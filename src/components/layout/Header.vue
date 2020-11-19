<template>
  <header class="header">
    <h1>News Corporation</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/metrics">Network Metrics</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.header {
  background: #00376e;
  color: #fff;
  text-align: center;
  padding: 10px;
}
.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
}
</style>