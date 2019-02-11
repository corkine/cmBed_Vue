<template xmlns:v-clipboard="http://www.w3.org/1999/xhtml">
  <el-row type="flex" class="row-bg" justify="center">
    <el-col :xs="20" :sm="15" :md="10"><div class="grid-content bg-purple">
      <transition name="el-fade-in-linear">
        <el-tooltip class="item" effect="dark" :content=result.url placement="bottom">

        <el-card id="result" class="result box-card" shadow="hover" v-clipboard:copy="result.url"
                 v-clipboard:success="copyToCP">
          <el-row type="flex" class="row-bg" justify="space-around">
            <i class="el-icon-picture-outline"> {{result.fileName}} <hr/>
            {{result.url.toString().length > 45 ? result.url.toString().substring(0,44) + "..." : result.url}}</i>
          </el-row>
        </el-card>

        </el-tooltip>
      </transition>
    </div></el-col>
    <el-button v-show="false"
      plain
      @click="copyToCP">
      偏移的消息
    </el-button>
  </el-row>
</template>

<script>
  export default {
    name: "Result",
    props: {
      result: Object
    },
    data() {
      return {
      }
    },
    methods: {
      copyToCP() {
        this.$notify({
          title: '成功',
          message: '网址已复制到剪贴板。',
          offset: 60,
          type: 'success'
        });

      }
    }
  }
</script>

<style scoped>
  .result {
    margin-top: 10px;
    line-height: 25px;
    text-align: left;
    border-radius: 5px;
    background-color: #ffffff;
    text-overflow: ellipsis;
    color: #787b7e;
  }
</style>
