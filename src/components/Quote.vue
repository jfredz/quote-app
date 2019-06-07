<template>
  <div>
    <div class="card" @click='deleteQuote(quote)'>
      <div class="card-body">
        {{ quote }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['quote', 'deleteQuote']
}
</script>

