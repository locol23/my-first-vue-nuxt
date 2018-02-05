<template>
  <div>
      <h1>Input</h1>
      <div class="input">
        <el-input placeholder="Please Input" v-model="input1"></el-input>
        <el-input placeholder="Please Input" v-model="input2"></el-input>
      </div>
      <h1>Rate</h1>
      <el-rate v-model="value1"></el-rate>

      <h1>Upload</h1>
      <el-upload
        class="csv-upload"
        drag
        action="http://localhost:3000"
        :on-preview="handlePreview"
        :on-remove="handleRemove"
        :file-list="fileList"
        >
        <i class="el-icon-upload"></i>
        <div class="el-upload__text">ファイルをドロップまたは<em>こちらをクリック</em></div>
        <div class="el-upload__tip" slot="tip">500KB以下でお願いします</div>
      </el-upload>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        input1: null,
        input2: null,
        value1: null,
        fileList: [{name: 'test.csv'}, {name: 'test2.csv'}],
      };
    },
    methods: {
      handleRemove(file, fileList) {
        console.log(file, fileList);
      },
      handlePreview(file) {
        console.log(file);
      }
    }
}
</script>

<style scoped>
.input >>>
  .el-input{
    margin: 10px auto;
  }
</style>
