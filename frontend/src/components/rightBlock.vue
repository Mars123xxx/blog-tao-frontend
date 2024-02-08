<template>
  <div class="col-lg-3">
    <div class="row g-4">
      <div class="col-sm-6 col-lg-12">
        <el-card>
          <el-button @click="this.$message('你好啊')">点我</el-button>
        </el-card>
      </div>
      <div class="col-sm-6 col-lg-12">
        <el-card>
          <el-button @click="this.$message({message:'别点我',type:'success'})">点我</el-button>
        </el-card>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>