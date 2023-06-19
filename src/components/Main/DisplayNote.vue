<template>
  <div class="container">
    <show-note
      v-for="note in notes"
      :key="note"
      :noteDisplay="note"
      @noteDelete="Delete"
    ></show-note>
  </div>
</template>

<script>
import ShowNote from "./ShowNote.vue";
export default {
  components: {
    ShowNote,
  },

  props: ["notes"],

  data() {
    return {};
  },

  methods: {
    Delete(note) {
      const remove = confirm('Are you sure you want to delete')

      if (remove) {
        const thisNote = this.notes
        const indexofNote = thisNote.indexOf(note)
        thisNote.splice(indexofNote, 1)
        alert('Note deleted successfully')
      }
    }
  }
};
</script>

<style></style>
