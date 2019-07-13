<template>
  <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <el-menu-item index="1">
      <nuxt-link to="/home">Home</nuxt-link>
    </el-menu-item>
    <el-menu-item index="2" v-if="!loggedIn" @click="login">Login</el-menu-item>
    <el-menu-item index="3" v-else @click="logout">Logout</el-menu-item>
  </el-menu>
</template>

<script>
  export default {
    data() {
      return {
        loggedIn: true,
        activeIndex: '1',
        activeIndex2: '1'
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      },
      login() {
        this.loggedIn = true;
      },
      logout() {
        this.loggedIn = false;
      }
    }
  }
</script>

<style>

</style>
