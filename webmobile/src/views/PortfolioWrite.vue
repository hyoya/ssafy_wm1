<template>
	<div>

		<!-- Editor -->
		<v-layout my-5>
			<v-flex column>
				<PFEditor/>
			</v-flex>
		</v-layout>


  </div>
</template>


<script>

import PFEditor from "../components/PFEditor"

export default {
	name: 'PortfolioWrite',
	components: {
		PFEditor,
	},
}
</script>
