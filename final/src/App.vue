<template>
  <div id="app">
    <Header></Header>
    <div id="left1">
      <Left></Left>
    </div>
    <div id="right1">
      <div id="form">
        <span><select style="width:60px;height:30px" id="Select">
          <option value="Get">GET</option>
          <option value="Post">POST</option>
          <option value="Put">PUT</option>
          <option value="Json">JSON</option>
        </select>
      <input type="text" v-model="loginInfo.message" style="width:200px;height:30px" placeholder="Please Enter The Url" />
      <button @click="submit"><span><b><font color="blue">Send</font></b></span></button><br/></span>
      </div>
      <div id="textfile">
        <div>
        <span>
          <font color="#184481"><h3>Request Result</h3></font><textarea cols="60" rows="14" v-model="responseResult" style="font-size:13px"></textarea>
        </span>
        </div>
      </div>
    </div>
    <Foot></Foot>
  </div>
</template>

<script>
import Foot from '@/components/FootLogo/Foot.vue'
import Header from '@/components/HeaderLogo/Header.vue'
import Left from '@/components/LeftLogo/Left.vue'
export default {
  name: 'App',
  components: {Foot, Header, Left},
  data () {
    return {
      loginInfo: {message: ''},
      info: null,
      index: -1, // 定义一个索引
      consequence: [],
      responseResult: []
    }
  },
  methods: {
    submit () {
      var obj = document.getElementById('Select')
      var ops = obj.value
      if (ops === 'Get') {
        if (this.loginInfo.message === '') {
          alert('Please Enter The Url,Thank')
          this.loginInfo.message = ''
        } else {
          this.get()
          alert('Success')
          this.loginInfo.message = ''
        }
      } else if (ops === 'Json') {
        this.json()
        alert('Success')
        this.loginInfo.message = ''
      } else {
        alert('Please Enter The Correct Method,Thanks')
        this.responseResult = ''
      }
      // var url = this.HOST + '/movie/in_theaters'
      // this.j = this.j + 1
      // this.$http.get(url).then(response => (this.responseResult = JSON.stringify(response.data.subjects[this.j].title))
      // ).catch(error => {
      // console.log(error)
      // this.errored = true
      // })
    },
    get () {
      var url = this.HOST + this.loginInfo.message
      this.index = this.index + 1 // 依次递增索引
      this.$http.get(url).then(response => (this.responseResult = JSON.stringify(response.data.subjects[this.index].title))
      ).catch(error => {
        console.log(error)
        this.errored = true
      })
    },
    json () {
      var url = this.HOST + '/movie/in_theaters'
      this.index = this.index + 1
      this.$http.get(url).then(response => (this.responseResult = JSON.stringify(response.data.subjects[this.index].title))
      ).catch(error => {
        console.log(error)
        this.errored = true
      })
      for (var item = 0; item < this.loginInfo.message.length; item++) {
        this.consequence = this.responseResult[item]
      }
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
  margin-top: -20px;
}
#left1 {
  width: 20%;
  height: 100%;
}
#right1 {
  width: 100%;
  height: 100%;
  position: relative;
  margin-top: 70px;
}
#search {
  width: 20%;
  float: left;
  margin-top: -10px;
}
#filter {
  margin-top: -10px;
  width: 80%;
  float: right;
}
</style>
