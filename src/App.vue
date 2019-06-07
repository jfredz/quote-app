<template>
  <div class="container">
		<div class='row'>
			<div class="col-lg-12">
				<Header></Header>
			</div> 
		</div>
    <div class='row quotes'>
			<div class="col-lg-6">
				<QuoteBox></QuoteBox>
			</div>
		</div>
		<Quotes></Quotes>
		<Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import QuoteBox from './components/QuoteBox.vue'
import Footer from './components/Footer.vue'
import Quote from './components/Quote.vue'
import Quotes from './components/Quotes.vue'
  export default {
		components: {
			Header,
			QuoteBox,
			Footer,
			Quote,
			Quotes
		}
  }
</script>

<style>
	.quotes {
		margin: 50px 0
	}
</style>
