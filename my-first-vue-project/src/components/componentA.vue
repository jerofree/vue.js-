<template>
  <div class="hello">
    <h1>{{msg}}</h1>
    <button v-on:click="onClickMe">Click!</button>
    <h1>{{msgfromfather}}</h1>
    <div class="box">
      <input type="button" value="按钮">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'hello',
    data () {
      return {
        msg: 'Hello from componentA',
      }
    },
    props:['msgfromfather'],
    methods:{
      onClickMe:function () {
      // alert(this.msgfromfather);
       this.$emit('child-tell-me-something',this.msg);
      }
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
