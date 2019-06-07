<template>
  <div>
    <h2>Quotes Added</h2>
    <div class="progress">
      <div class="progress-bar" :style="{ width: progress + '%' }" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
        <span v-if='progress'>{{ progress / 10 }}/10</span>
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../main'
export default {
  data() {
    return {
      progress: 0
    }
  },
  methods: {
    updateProgressBar() {
      this.progress = this.progress + 10
    }
  },
  created() {
    eventBus.$on('quotedAdded', () => {
      this.updateProgressBar()
    }),
    eventBus.$on('deletedQuote', () => {
      this.progress = this.progress - 10
    })
  }
}
</script>

<style>

</style>
