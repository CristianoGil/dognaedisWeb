
<template>
	<div className="col-3">

			<!-- HORIZONTAL LAYOUT -->
			<div class="vx-col md:w-1/2 w-full mb-base">
				<vx-card title="Register number" >
					<form>
						<div class="vx-row mb-6">
							<div class="vx-col sm:w-1/3 w-full">
								<span>Full name</span>
							</div>
							<div class="vx-col sm:w-2/3 w-full">
								<vs-input class="w-full" v-validate="'required'"   placeholder="Fogao ilutres" name="name"  autofocus type="text" v-model="name" />
								<span class="text-danger text-sm" v-show="errors.has('name')">{{ errors.first('name') }}</span>
							</div>
						</div>

						<div class="vx-row">
							<div class="vx-col sm:w-2/3 w-full ml-auto">
								<vs-button type="filled" @click.prevent="submitForm"  class="mr-3 mb-2 block">Register</vs-button>
							</div>
						</div>
					</form>
				</vx-card>
			</div>

	</div>
</template>


<script>

import axios from '@/axios.js'

export default{
  data () {
    return {
			name: '',
    }
  },
	methods: {
		submitForm () {
			this.$validator.validateAll().then(result => {
				if (result) {

					// if form have no errors
					alert('form submitted!');

				} else {
				
					// form have errors
				}
			})
		}
	}
}
</script>
