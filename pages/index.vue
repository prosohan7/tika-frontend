<template>
 <div>
 	<h1>Check:{{apiValue}}</h1>
 	<Tutorial/>
 </div>
</template>

<script>
export default {
	data() {
		return {
			apiValue: ''
		}
	},
	mounted() {
		this.testBackendRequest();
	},
	methods: {
		testBackendRequest() {
			this.$axios.get('/test').then(res => {
				console.log(res.data);
				this.apiValue = res.data;
			});
		}
	}
}
</script>
