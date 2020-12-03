<template>
  <div>
    <ul>
      <li
        :class="{active: item.active}"
        v-for="(item,index) in navList"
        :key="index"
        @click="changeNav(item)"
      >
        <transition name="hover">
          <div>{{item.name}}</div>
        </transition>
      </li>
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

<style lang="less" scoped>
ul {
  height: 112px;
  text-align: center;
  li {
    display: inline-block;
    line-height: 112px;
    list-style: none;
    color: #2c91ed;
    font-size: 18px;
    font-weight: 700;
    cursor: pointer;
    & > div {
      padding: 0 15px;
    }
  }
  li li.active div,
  li div:hover {
    color: #fff;
    background-color: #ff7f1c;
  }
  .hover-enter,
  .hover-leave-to {
    background-color: rgba(255 127 28, 0);
    color: green;
  }
  .hover-enter-active,
  .hover-leave-active {
    background-color: rgba(255 127 28, 1);
    color: aqua;
    transition: all 13s ease;
  }
}
</style>