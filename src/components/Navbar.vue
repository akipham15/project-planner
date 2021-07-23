<template>
  <nav class="main-nav">
      <router-link :to="{name: 'Home'}">Home</router-link>
      <router-link :to="{name: 'AddProject'}">AddProject</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style>
    .main-nav {
        text-align: center;
        margin: 40px auto;
        font-weight: bold;
    }
    .main-nav a {
        text-decoration: none;
        display: inline-block;
        margin: 0 10px;
        font-size: 20px;
        color: #999;
    }
    a.router-link-active {
        border-bottom: 2px solid #00ce89;
        padding-bottom: 4px;
    }
</style>