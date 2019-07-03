<template>
	<div>
		<!-- Header -->
		<v-layout column>
			<v-flex xs12>
				<MyHeader/>
			</v-flex>
		</v-layout>

		<!-- Editor -->
		<v-layout my-5>
			<v-flex column>
				<PFEditor/>
			</v-flex>
		</v-layout>


		<!-- Footer -->
    <v-layout column>
      <v-flex xs12>
        <MyFooter/>
      </v-flex>
    </v-layout>

  </div>
</template>


<script>
import MyHeader from "../components/MyHeader"
import MyFooter from "../components/MyFooter"
import PFEditor from "../components/PFEditor"

export default {
	name: 'PortfolioWrite',
	components: {
    MyHeader,
    MyFooter,
		PFEditor,
	},
}
</script>
