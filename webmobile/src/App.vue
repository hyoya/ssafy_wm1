<template>
  <v-app>
    <v-content>
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
import store from './store'
import MyHeader from "./components/MyHeader"
import MyFooter from "./components/MyFooter"

export default {
	name: 'App',
	store,
  components : {
    MyHeader,
    MyFooter
  },
	data() {
		return {
			//
		}
	}
}
</script>
