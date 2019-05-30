<template>
  <div id="app">
    <router-view>
      
    </router-view>
  </div>
</template>

<style>
html, body, #app, .el-container{
  height: 100%;
}

body{
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333333;
}

.menu-a{
  color: #fff;
  text-decoration-line: none;
}

.el-aside{
  background-color: #545c64;
}

.el-header{
  padding: 0;
  float: right;
  background-color: #ffffff;
}

.el-menu{
  width: 200px;
  text-align: left;
  border-right: none;
}

.el-menu > a{
  color:#fff ;
}

.el-container{
  background: #f0f2f5;
}

#nav {
  height: 50px;
}

.user-info{
  float: right;    
  line-height: 60px;
  font-size: 14px;
}
</style>
