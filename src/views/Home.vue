<template>
  <div class="page">
    <h2>Home Page</h2>
    <el-button type="primary" class="not-found-btn-gohome" @click="testhttp()">测试调用</el-button>
  </div>
</template>

<script>
import axios from 'axios'
import mock from '@/mock/mock.js'
import router from '@/router/index.js'
export default {
  name: 'Home',
  methods: {
      testhttp()
      {
          //axios.post('http://localhost:8080/api')
          axios(
              {
                  method: 'post',
                  url: 'http://localhost:8000/api2',
                  headers:{
                      'token':'1234'
                  }
              }).then(function(res) {
                  alert(JSON.stringify(res.data));
                  router.push("404")
          }).catch(function(res) {
             alert(res);
          });
      }
  }
}
</script>