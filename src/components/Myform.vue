<template>
  <div id="app">

  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name:</label><br>
      <input id="name" type="text" v-model="name" required/>
    </div>
    <div>
      <label for="email">Email:</label><br>
      <input id="email" type="email" v-model="email" required/>
    </div>
    <div>
      <label for="caps">HOW DO I TURN OFF CAPS LOCK:</label><br>
      <textarea id="caps" v-model="caps" required></textarea>
    </div>
    <button :class="[name ? activeClass : '']" type="submit">Submit</button>
    <div>
      <h3>Response from server:</h3>
      <pre>{{ response }}</pre>
    </div>
  </form>
  
</div>


</template>

<script>
import axios from 'axios'

export default {
  name:'App',
  data() {
    return {

      name: '',
      email: '',
      caps: '',
      response: '',
      activeClass: 'active'
    }
  },
  methods: {
    submitForm() {
      axios.post('//jsonplaceholder.typicode.com/posts', {
        name: this.name,
        email: this.email,
        caps: this.caps
      }).then(response => {
        this.response = JSON.stringify(response, null, 2)
      }).catch(error => {
        this.response = 'Error: ' + error.response.status
      })
   
  
    }
  }
}

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
