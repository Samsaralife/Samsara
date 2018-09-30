<template>
  <div id="app">
    <div>
    <h1>Index</h1>
    <input type="text" v-model="loginInfo.message" placeholder="Please Enter The Url" />
    <button @click="submit">Submit</button><br/>
    <section>
      <h3>Request Result</h3>
      <p>
        <textarea cols="70" rows="7" v-model="responseResult"></textarea>
        <button @click="send">Send</button>
      </p>
    </section>
    </div>
    <hr/>
    <div>
      <h2>Consequence</h2>
      <p></p>
      <h2><p>{{consequence}}</p></h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      loginInfo: {message: ''},
      info: null,
      j: -1,
      consequence: [],
      responseResult: []
    }
  },
  methods: {
    submit () {
      var url = this.HOST + '/movie/in_theaters'
      this.j = this.j + 1
      this.$http.get(url).then(response => (this.responseResult = JSON.stringify(response.data.subjects[this.j].title))
      ).catch(error => {
        console.log(error)
        this.errored = true
      })
    },
    send () {
      this.consequence = this.responseResult
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
