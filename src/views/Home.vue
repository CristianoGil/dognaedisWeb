<template>
	<div className="col-3">

			<!-- HORIZONTAL LAYOUT -->
			<div class="vx-col md:w-1/2 w-full mb-base">
				<vx-card title="Recharge" >
						<div class="vx-row mb-6">
							<div class="vx-col sm:w-1/3 w-full">
								<span>Mobile</span>
							</div>
							<div class="vx-col sm:w-2/3 w-full">
								<vs-input class="w-full" v-validate="'required|min:9|max:9'"   placeholder="845566333" name="Mobile Number"  autofocus type="number" v-model="mobileNumber" />
								<span class="text-danger text-sm" v-show="errors.has('mobileNumber')">{{ errors.first('mobileNumber') }}</span>

							</div>
						</div>

						<div class="vx-row mb-6">
							<div class="vx-col sm:w-1/3 w-full">
								<span>Token</span>
							</div>
							<div class="vx-col sm:w-2/3 w-full">
								<vs-input class="w-full" v-validate="'required|min:12|max:12'"  placeholder="123456789032" name="tokenNumber"  type="number" v-model="tokenNumber" />
								<span class="text-danger text-sm" v-show="errors.has('tokenNumber')">{{ errors.first('tokenNumber') }}</span>
							</div>
						</div>
						<div class="vx-row">
							<div class="vx-col sm:w-2/3 w-full ml-auto">
								<vs-button type="filled" @click.prevent="submitForm"  class="mr-3 mb-2 block">Submit</vs-button>
							</div>
						</div>
				</vx-card>
			</div>

	</div>
</template>


<script>
export default{
  data () {
    return {
			mobileNumber: '',
			tokenNumber: ''
    }
  },
	methods: {
		submitForm () {
			this.$validator.validateAll().then(result => {
				if (result) {

					// if form have no errors
					alert('form submitted!')

				} else {


					// form have errors
				}
			})
		}
	}
}
</script>
