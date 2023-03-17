<script setup lang="ts">
import {ref} from 'vue'
import type { TabsPaneContext } from 'element-plus'
const activeName=ref("first")
function handleClick (tab: TabsPaneContext, event: Event){
  console.log(tab, event)
}
</script>

<template>
  <el-container class="fill">
    <el-header class="header center">头部</el-header>
    <el-main class="main center">
      <el-tabs v-model="activeName" class="demo-tabs" tab-position="left" @tab-click="handleClick">
        <el-tab-pane label="User" name="first">User</el-tab-pane>
        <el-tab-pane label="Config" name="second">Config</el-tab-pane>
        <el-tab-pane label="Role" name="third">Role</el-tab-pane>
        <el-tab-pane label="Task" name="fourth">Task</el-tab-pane>
      </el-tabs>
    </el-main>
    <el-footer class="footer center">状态栏</el-footer>
  </el-container>
</template>

<style scoped>
.fill {
  width: 100%;
  height: 100%;
}
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
.header {
  background-color: aliceblue;
  border-bottom: 1px solid #cfcdcd;
}
.main {
  background-color: white;
  overflow-y: auto;
}
.footer {
  border-top: 1px solid #cfcdcd;
  background-color: beige;
  height: 35px;
}
.demo-tabs{
  height: 100%;
  width: 100%;
}
.demo-tabs > .el-tabs__content {
  padding: 32px;
  color: #6b778c;
  font-size: 32px;
  font-weight: 600;
}
</style>
