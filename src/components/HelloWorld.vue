<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ time }}</h2>
    <h3>{{ hello }}</h3>
  </div>
</template>

<script>
import * as wasm from "rust-wasm";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      time: '2012'
    }
  },
  computed: {
    hello: function() {
      return wasm.greet()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
