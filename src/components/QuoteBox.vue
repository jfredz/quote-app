<template>
	<div>
		<div class="input-group">
			<div class="input-group-prepend">
				<span class="input-group-text">Quote</span>
			</div>
			<textarea class="form-control" aria-label="With textarea" v-model='newQuote'></textarea>
		</div>
		<button type="button" @click='addQuote' class="btn btn-primary">Add Quote</button>
	</div>
</template>

<script>
import { eventBus } from '../main'
export default {
	data() {
		return {
			newQuote: ''
		}
	},
	methods: {
		addQuote() {
			eventBus.$emit('addedQuote', this.newQuote)
			this.newQuote = ''
		}
	}
}
</script>
<style scoped>
	.btn {
		margin-top: 10px;
	}
</style>

