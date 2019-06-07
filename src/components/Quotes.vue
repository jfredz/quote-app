<template>
	<div class="row">
		<div v-for='quote in quotes' :key='quote' class="col-md-3">
			<Quote :quote='quote' :deleteQuote='deleteQuote' />
		</div>
	</div>
</template>

<script>
import { eventBus } from '../main'
import Quote from './Quote.vue'

export default {
	data() {
		return {
			quotes: []
		}
	},
	components: {
		Quote
	},
	methods: {
		addQuote(quote) {
			this.quotes.push(quote)
			eventBus.$emit('quotedAdded')
		},
		deleteQuote(quote) {
			let index = this.quotes.indexOf(quote)
			this.quotes.splice(index, 1);
			eventBus.$emit('deletedQuote')
		}
	},
	created() {
		eventBus.$on('addedQuote', (quote) => {
			if(this.quotes.length >= 10) {
				alert('You can not add more quotes! Please delete some.')
			} else {
				if(!quote.length < 1 ) this.addQuote(quote)
			}
		})
	}
}
</script>
