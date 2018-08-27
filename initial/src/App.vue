<template>
  <div id="app">
    <div class="header">
      <router-link to="/a">Go to A</router-link>
      <router-link to="/b">Go to b</router-link>
      <router-link to="/c">Go to c</router-link>
    </div>
    <router-view></router-view>
    <div class="footer">footer</div>
  </div>
</template>

<style>
  #app {
    text-align: center;
    font-size: 20px;
  }
  .header {
    height: 50px;
    background-color: #ebebeb;
    margin-bottom: 50px;
  }
  .footer {
    height: 50px;
    background-color: #ebebeb;
    margin-top: 70px;
  }
</style>
