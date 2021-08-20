<template>
<div id="hello-vue" class="demo">
  <p>{{ msg }}</p>
  <p>Count: {{ count }} <button v-on:click="increment">Up vote</button></p>
  <p><input v-model="inputMessage" placeholder="Input message here"/> {{ inputMessage }}</p>
  <div id="list-rendering">
    <ul>
      <li v-for="item in theList" v-bind:key="item.id">
        {{ item.text }}
      </li>
    </ul>
  </div>
  <p>Computed: {{ computedCount }}</p>
  <div v-if="Math.random() > 0.5">
    Now you see me
  </div>
  <div v-else>
    Now you don't
  </div>
</div>
</template>

<script>
export default {
  name: 'MyComponent',
  props: {
    msg: String
  },
   data() {
    return {
      inputMessage: '',
      count : 4,
      theList : [
        {id : 1, text: "a"},
        {id : 2, text: "b"},
        {id : 3, text: "c"}
      ]
    }
  },
  methods: {
    increment() {
      // `this` will refer to the component instance
      this.count++
    }
  },
  computed: {
    // a computed getter
    computedCount() {
      // `this` points to the vm instance
      return this.count+100
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.demo {
  font-family: sans-serif;
  border: 1px solid #eee;
  border-radius: 2px;
  padding: 20px 30px;
  margin-top: 1em;
  margin-bottom: 40px;
  user-select: none;
  overflow-x: auto;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
