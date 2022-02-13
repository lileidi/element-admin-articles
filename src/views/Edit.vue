<template>
  <div class="edit">
    <el-form @submit.native.prevent="saveArticles" ref="form" :model="articles" label-width="100px">
  <el-form-item label="文章标题">
    <el-input v-model="articles.title"></el-input>
  </el-form-item>
  <el-form-item label="文章内容">
    <el-input v-model="articles.body"></el-input>
  </el-form-item>
  <el-form-item>
    <el-button type="primary" native-type="submit">保存</el-button>
    <el-button>取消</el-button>
  </el-form-item>
</el-form>
  </div>
</template>


<script>
  export default {
    data() {
      return {
        articles: {
        }
      }
    },
    methods: {
      fetch(){
        this.$http.get(`articles/${this.$route.params.id}`).then(res=>{
          this.articles = res.data
        })
      },
      saveArticles(){
        // 第一个参数articles是接口路径，第二个参数是对象
        this.$http.put(`articles/${this.$route.params.id}`,this.articles).then(() =>{
          // console.log(res.data);
            this.$message({
            message: '文章更新成功',
            type: 'success'
          });
          this.$router.push('/articles/index')
        })
        // console.log(this.articles);
      }
    },
    created(){
      this.fetch()
    }
  }
</script>
