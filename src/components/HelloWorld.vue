<template>
  <div class="hello">
    <h1>{{loginIn }}</h1>
    <h2>{{loginOut}}</h2>
    <button @click='loginout'>登出</button>
    <h2>Essential Links</h2>
    <h2>Ecosystem</h2>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      loginIn: 'Welcome to Your Vue.js App',
      loginOut:""
    }
  },
  methods:{
    loginout:function(){
      this.qa.login.loginOut();
    }
  },
  mounted:function(){
    //告诉qa现在处理的是那个组件
    this.qa.v(this);
    this.qa.login.loginIn({
      success:function(res,bind){
        bind(res+'hello');
      }
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
