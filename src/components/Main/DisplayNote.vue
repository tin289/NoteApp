<template>
  <div class="container">
    <show-note v-for="note in notes" :key="note" :note="notes"></show-note>
  </div>
</template>

<script>
import ShowNote from './ShowNote.vue'
export default {
components: {
    ShowNote
},

props: {
    title: {
      type: String,
    },
    des: {
      type: String,
    },
    link: {
      type: String,
    },
  },

data() {
  return {
    notes: [
      {
        displayTitle: this.title,
        displayDes: this.des,
        displayLink: this.link
      }
    ]
  }
}
}
</script>

<style>

</style>