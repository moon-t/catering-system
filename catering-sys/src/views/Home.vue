<template>
<el-container>
      <el-aside width="200px">
        <el-menu
          default-active="2"
          class="el-menu-vertical-demo"
              
          background-color="#545c64"
          text-color="#fff"
          active-text-color="#ffd04b">
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>  
              <span>菜单一
              </span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">
                 
              <router-link class="menu-a" to="/"><span>Home</span></router-link>
              </el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>  
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <router-link class="menu-a" to="/about">About</router-link>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-container>
        <el-header padding="0px"> 
          <div class="user-info">
            <i class="el-icon-user"></i>
            <span>admin</span>
            <el-divider direction="vertical"></el-divider>
            <router-link class="menu-a" to="/login"><span>loginout</span></router-link>
          </div>
        </el-header>
        <el-main>
          <el-breadcrumb separator="/">
            <el-breadcrumb-item :to="{ path: '/' }">菜单一</el-breadcrumb-item>
            <el-breadcrumb-item><a href="/">活动管理</a></el-breadcrumb-item>
            <el-breadcrumb-item>活动列表</el-breadcrumb-item>
            <el-breadcrumb-item>活动详情</el-breadcrumb-item>
          </el-breadcrumb>
          <router-view/>
        </el-main>
      </el-container>
    </el-container>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
