
<template>

  <div>

    <ImgBanner imgSrc="https://source.unsplash.com/random/1600x900">
      <div style="line-height:1.2em; font-size: 6vw;" slot="text">오늘이 내일을 만든다</div>
    </ImgBanner>
    <v-container>

      <!-- About Me -->
      <v-layout my-5>
        <v-flex xs12 sm8>
          <h2 class="headline mb-3 text-xs-center" >About Me</h2>
          <p class="mr-4" style=" font-size: 2vw;">
            Call Me Hyoya! I'm Developer!</br>
            안녕하세요 결정에 대한 책임의 무게를 아는 개발자 서효정입니다.</br>
            JAVA를 주로 사용하고, C, C++도 좋아합니다.
          </p>
        </v-flex>
        <v-flex sm4>
          <v-img :src="getImgUrl('prof.jpg')" aspect-ratio="1.5" class="hidden-xs-only"/>
        </v-flex>
      </v-layout>

      <!-- Portfolio -->
      <v-layout my-5>
        <v-flex xs12>
          <h2 class="headline my-5 text-xs-center">Portfolio</h2>
          <PortfolioList></PortfolioList>
        </v-flex>
      </v-layout>

      <!-- Post -->
      <v-layout my-5>
        <v-flex xs12>
          <h2 class="headline my-5 text-xs-center">Post</h2>
          <PostList :column="2"></PostList>
        </v-flex>
      </v-layout>


      <!-- Github -->
      <v-layout my-5>
        <v-flex xs12>
          <h2 class="headline my-5 text-xs-center">Project</h2>
          <RepositoryList></RepositoryList>
        </v-flex>
      </v-layout>

    </v-container>


  </div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'
import PostList from '../components/PostList'
import RepositoryList from '../components/RepositoryList'

export default {
	name: 'HomePage',
	components: {
		ImgBanner,
		PortfolioList,
		PostList,
		RepositoryList,
	},
	methods: {
		getImgUrl(img) {
			return require('../assets/' + img)
		}
	},
}
</script>
