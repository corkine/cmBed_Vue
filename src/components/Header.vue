<template>
  <el-menu :default-active="activeIndex"
           class="el-menu-demo"
           mode="horizontal"
           @select="handleSelect"
           background-color="#545c64"
           text-color="#ffffff"
           active-text-color="#ffffff"
           title="MAZJ's Picture Bed"
  >
    <el-menu-item index="0"><span id="title">🐴 图床</span></el-menu-item>
    <el-menu-item index="1">Home</el-menu-item>
    <el-menu-item index="2">About</el-menu-item>
    <el-row type="flex" justify="end" class="headerTitle">
      <p>A Muninn Project</p>
    </el-row>
    <!--<el-submenu index="4">
      <template slot="title">Thanks</template>
      <el-menu-item index="4-1">Spring Boot</el-menu-item>
      <el-menu-item index="4-2">Vue</el-menu-item>
      <el-menu-item index="4-3">Element</el-menu-item>
      <el-submenu index="4-4">
        <template slot="title">服务提供商</template>
        <el-menu-item index="4-4-1">阿里云 OSS</el-menu-item>
        <el-menu-item index="4-4-2">阿里云 CDN</el-menu-item>
        <el-menu-item index="4-4-3">天翼云 HOST</el-menu-item>
      </el-submenu>
    </el-submenu>-->
  </el-menu>
</template>

<script>
  export default {
    name: "Header",
    data() {
      return {
        activeIndex: '1',
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style scoped>
  .headerTitle {
    margin-top: 3px;
    margin-right: 30px;
    color: white;
  }
  .el-menu-demo {
    width: 100%;
  }
  #title {
    font-size: 24px;
    letter-spacing: 3px;
  }
</style>
