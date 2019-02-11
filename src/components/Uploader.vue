<template>
  <div>
    <el-upload
      class="upload"
      drag
      name="file"
      :xs="20" :sm="15" :md="10"
      :action=UploadUrl
      :before-upload="doBeforeUpload"
      :on-success="doOnSuccess"
      :on-progress="doOnProgress"
      :on-error="doOnError"
    >
      <i class="el-icon-upload"></i>
      <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>
      <div class="el-upload__tip" slot="tip">可上传多种类型文件，文件大小不得超过 5MB.</div>
    </el-upload>
    <el-button v-show="false"
               plain>
      偏移的消息
    </el-button>
    <Result v-for="(result, index) in results" :key="index" :result="result"/>
  </div>
</template>

<script>
  import Result from "./Result";
  export default {
    name: "Uploader",
    components: {Result},
    props: ["UploadUrl"],
    data() {
      return {
        results: [
          //{fileName: "文件名 - 点击卡片自动复制到剪贴板", url:"http://static2.mazhangjing.com/23333333333333333333333333333333"}
        ]
      }
    },
    methods: {
      doOnSuccess(response, file, fileList) {
        console.log("doOnSuccess");
        this.notice("文件上传成功","点击下方卡片以将网址复制到剪贴板");
        this.results.splice(this.results.length,0,response)
      },
      doOnProgress(event, file, fileList) {
        /*console.log("doOnProgress")
        console.log(event)
        console.log(file)*/
      },
      doOnError(err, file, fileList) {
        console.log("error");
        this.notice("文件上传失败","请打开控制台查看错误详情",'warning');
        console.log(err)
      },
      doBeforeUpload(file) {
        /*console.log("Checking file ")
        console.log(file)*/
      },
      notice(title, message, type = 'success') {
        this.$notify({
          title: title,
          message: message,
          offset: 60,
          type: type
        });
      }
    }
}
</script>

<style scoped>
  .upload {
    margin-top: 50px;
    margin-bottom: 50px;
  }
</style>
