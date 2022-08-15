<template>
  <el-container>
    <el-aside width="200px" v-show="check" 
      >Available Fields
      <template>
    <el-checkbox v-model="checked1" @click="change">Email Adress</el-checkbox>
    <el-checkbox v-model="checked2" @click="change">Name</el-checkbox>
    <el-checkbox v-model="checked3" @click="change">Phone Number</el-checkbox>
      </template>
    <el-button type="success" @click="submit">PUBLISH</el-button>
    </el-aside>
    <el-main>
        <template>
            Simple Body 
            <div>
        <el-input v-model="input" placeholder="Email" v-if="checked1"></el-input>
        <el-input v-model="input" placeholder="Name" v-if="checked2"></el-input>
        <el-input v-model="input" placeholder="Phone" v-if="checked3"></el-input>
            </div>
        </template>
        
    </el-main>
  </el-container>
</template>

<script>
export default {
  name: "Test",
  data () {
      return { 
        check:true,
        checked1:false,
        checked2:false,
        checked3:false,
        input: ''
      };
    },
    methods:{
        change(){
            checked1 ? false:true;
            checked2 ? false:true;
            checked3 ? false:true;
        },
        submit(){
           this.check=true;
        }
    }
};

</script>

<style scoped>
.el-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: left;
  line-height: 60px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 60px;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>