<template>
  <div>
    <ul>
      <transition name="hover">
        <li
          :class="{active: item.active}"
          v-for="(item,index) in navList"
          :key="index"
          @click="changeNav(item)"
        >{{item.name}}</li>
      </transition>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Nav",
  data() {
    return {
      navList: [
        {
          name: "Home",
          active: true
        },
        {
          name: "Company",
          active: false
        },
        {
          name: "Steel Product",
          active: false
        },
        {
          name: "Hardware",
          active: false
        },
        {
          name: "Machinery",
          active: false
        },
        {
          name: "Contact Us",
          active: false
        },
        {
          name: "Join Us",
          active: false
        }
      ]
    };
  },
  methods: {
    changeNav(item) {
      this.navList.map(it => {
        if (item.name === it.name) {
          it.active = true;
        } else {
          it.active = false;
        }
      });
    }
  }
};
</script>

<style scoped>
ul {
  height: 112px;
  text-align: center;
}
li {
  display: inline-block;
  line-height: 112px;
  list-style: none;
  padding: 0 15px;
  color: #2c91ed;
  font-size: 18px;
  font-weight: 700;
  cursor: pointer;
}
li.active,
li:hover {
  color: #fff;
  background-color: #ff7f1c;
}
.hover-enter,
.hover-leave-to {
  background-color: rgba(255 127 28,0);
}
.hover-enter-active,
.hover-leave-active {
  background-color: rgba(255 127 28,1);
}
</style>