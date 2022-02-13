<template>
  <div id="app">
    <el-container style="height: 500px; border: 1px solid #eee">
  <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
    <el-menu router :default-openeds="['1', '2']">
      <el-submenu index="1">
        <template slot="title"><i class="el-icon-reading"></i>文章管理</template>
          <el-menu-item index="/articles/index">文章列表</el-menu-item>
          <el-menu-item index="/articles/create">添加文章</el-menu-item>
      </el-submenu>
      <!-- <el-submenu index="2">
        <template slot="title"><i class="el-icon-menu"></i>借阅管理</template>
          <el-menu-item index="2-1">借书</el-menu-item>
          <el-menu-item index="2-2">还书</el-menu-item>
      </el-submenu> -->
    </el-menu>
  </el-aside>
  
  <el-container>
    <el-header style="text-align: right; font-size: 12px">
      <el-dropdown>
        <i class="el-icon-setting" style="margin-right: 15px"></i>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>查看</el-dropdown-item>
          <el-dropdown-item>新增</el-dropdown-item>
          <el-dropdown-item>删除</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
      <span>王小虎</span>
    </el-header>
    
    <el-main>
      <router-view></router-view>
    </el-main>
  </el-container>
</el-container>
  </div>
</template>

<style>
  .el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  
  .el-aside {
    color: #333;
  }
</style>
