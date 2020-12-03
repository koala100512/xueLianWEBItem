<template>
  <div class="container">
    <nav-table class="nav"></nav-table>
  </div>
</template>

<script>
import Nav from './common/nav'
export default {
    name: 'Home',
    components: {
      NavTable: Nav
    }
}
</script>

<style scoped>
.container {
  width: 100%;
}

</style>

</style>