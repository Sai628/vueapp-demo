<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <ul>
        <li v-for="user in users">
          {{user.firstname}} {{user.lastname}}
        </li>
      </ul>
    </div>
    <div>
      <input type="text" v-model="input_val">
    </div>
    <div>
      Input Value: <span v-text="input_val"></span>
    </div>
    <br/>
    <div>
      <button class="btn btn-primary" v-on:click="counter++">You're clicked this button {{counter}} times!</button>
    </div>
    <br/>
    <div>
      <span v-bind:title="span_message">Hover your mouse over me for a few seconds to see my dynamically bound title!</span>
    </div>
    <br/>
    <div>
      <p v-if="seen">Now you see me</p>
    </div>
    <br/>
    <div>
      <p>{{ msg }}</p>
      <button v-on:click="reverseMessage">Reverse Message</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data: function() {
    return {
      msg: 'Welcome to Your Vue.js App',
      users: [
        {firstname: 'Sebastian', lastname: 'Eschweiler'},
        {firstname: 'Bill', lastname: 'Smith'},
        {firstname: 'John', lastname: 'Porter'}
      ],
      input_val: '',
      counter: 0,
      span_message: 'You loaded this page on ' + new Date(),
      seen: true
    }
  },
  methods: {
    reverseMessage: function() {
      this.msg = this.msg.split('').reverse().join('')
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
