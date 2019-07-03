<style>
.btn-to-top {
  width: 60px;
  height: 60px;
  padding: 10px 16px;
  border-radius: 50%;
  font-size: 22px;
  line-height: 22px;
}
</style>


<template>
  <v-app>
    <v-content>

      <back-to-top bottom="50px" right="50px">
  <button type="button" class="btn btn-info btn-to-top"><i class="fa fa-chevron-up"></i></button>
</back-to-top>
      <!-- Header -->
      <v-layout column>
        <v-flex xs12>
          <MyHeader/>
        </v-flex>
      </v-layout>

      <router-view/>

      <!-- Footer -->
      <v-layout column>
        <v-flex xs12>
          <MyFooter/>
        </v-flex>
      </v-layout>

    </v-content>
  </v-app>
</template>

<script>
import Vue from 'vue'
import BackToTop from 'vue-backtotop'
import store from './store'
import MyHeader from "./components/MyHeader"
import MyFooter from "./components/MyFooter"

export default {
  name: 'App',
  store,
  components : {
    MyHeader,
    MyFooter,
    BackToTop,
  },

  data() {
    return {
      browser : BrowserDetect
    };
  },
  beforeCreate() {
    if(browser !== 'Chrome') {
      alert("크롬만 지원")
    }
  }
}
</script>
