<template>
  <el-container style="height: 100%; border: 1px solid #42b983">
    <el-aside :width="aside_width"  style="height: 100vh ; background-color: #545c64;margin-left: -1px;">
      <Aside :isCollapse="isCollapse"></Aside>
    </el-aside>

    <el-container style="height: 100%;color: #9797ef">
      <el-header style="text-align: right; font-size: 12px; height: 100%; border-bottom: rgb(2,8,159) 1px solid">
        <Header @doCollapse="doCollapse" :icon="icon"></Header>
      </el-header>

      <el-main style="height: 100%;">
<!--      <Main></Main>-->
        <router-view/>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
import Aside from "@/components/Aside";
import Header from "@/components/Header";
//import Main from "@/components/Main";
export default {
  name: "index",
  components:{Aside,Header},
  data(){
    return{
      isCollapse:false,
      aside_width:'200px',
      icon:'el-icon-s-fold'
    }
  },
  methods:{
    doCollapse(){
      console.log(1111)
      this.isCollapse = !this.isCollapse
      if(this.isCollapse){//收缩
        this.aside_width = '64px'
        this.icon='el-icon-s-unfold'
      }else{//打开
        this.aside_width = '200px'
        this.icon="el-icon-s-fold"
      }
    }
  }
}
</script>

<style scoped>
.el-header {
  background-color: #7bc8d2;
  background-image: ;
  color: #333;
  line-height: 60px;
}
.el-main{
  padding: 5px;
}
.el-aside {
  color: #333;
}
</style>