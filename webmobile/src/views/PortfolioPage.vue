<template>
  <div>
    <!-- Header -->
    <v-layout column>
      <v-flex xs12>
        <MyHeader/>
      </v-flex>
    </v-layout>

    <ImgBanner imgSrc="https://source.unsplash.com/5brvJbR1Pn8/1600x900">
      <div style="line-height:1.2em;font-size:1.2em;" slot="text">Portfolio</div>
    </ImgBanner>
    <v-container>

      <!-- Portfolio -->
      <v-layout>
        <v-flex xs12>
          <PortfolioList :limits="6" :load-more="true"></PortfolioList>
        </v-flex>
      </v-layout>

    </v-container>

    <!-- Footer -->
    <v-layout column>
      <v-flex xs12>
        <MyFooter/>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'
import MyHeader from "../components/MyHeader"
import MyFooter from "../components/MyFooter"

export default {
	name: 'PortfolioPage',
	components: {
		ImgBanner,
		PortfolioList,
    MyHeader,
    MyFooter
	},
}
</script>
