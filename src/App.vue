<template>
  <div id="app">
    <Header/>
    <Uploader :UploadUrl="Url" />
    <div id="footer">
      <p>Designed By <a href="http://www.mazhangjing.com">Corkine Ma</a>, Programming with <a href="https://www.scala-lang.org/">Scala</a>
        and <a href="http://www.java.com">Java</a>,  Stored in AliYun OSS</p>
      <p>Powered By <a href="http://spring.io">Spring Boot</a> Web FrameWork,
        <a href="http://vuejs.org">Vue</a> FrameWork and <a href="http://element-cn.eleme.io">Element</a> UI Library</p>
    </div>
    <div id="footerBar"></div>
  </div>
</template>

<script>

import Header from "./components/Header";
import Uploader from "./components/Uploader";
import Result from "./components/Result";
export default {
  name: 'App',
  components: {
    Result,
    Uploader,
    Header
  },
  data() {
    return {
      //Url: "http://localhost:8080/api/upload"
      Url: "api/upload"
    }
  }
}
</script>

<style>
#app {
  font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
html, body {
  margin: 0;
  padding: 0;
}
#footer {
  position: fixed;
  bottom: 0;
  height: 66px;
  width: 100%;
  font-size: 10px;
  color: #919191;
  text-decoration-line: none;
  line-height: 10px;
}
#footer a {
  text-decoration-line: none;
  color: #606a75;
}
#footerBar {
  position: fixed;
  bottom: 0;
  height: 8px;
  width: 100%;
  background: #555c64;
}
</style>
