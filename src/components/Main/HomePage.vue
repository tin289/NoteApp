<template>
  <div class="container">
    <the-header></the-header>

    <create-note @sendData="submitData"></create-note>

    <display-note :notes="notes"></display-note>
  </div>
</template>

<script>
import CreateNote from "./CreateNote.vue";
import DisplayNote from "./DisplayNote.vue";
import TheHeader from "./TheHeader.vue";

export default {
  components: {
    TheHeader,
    CreateNote,
    // ShowNote,
    DisplayNote,
  },

  data() {
    return {
      notes: [
        // {
        //   title: "",
        //   des: "",
        //   link: "",
        // },
        {
          title: "1",
          des: "1",
          link: "https://www.google.com.vn/?hl=vi",
        },
        {
          title: "2",
          des: "2",
          link: "https://www.google.com.vn/?hl=vi",
        },
        {
          title: "3",
          des: "3",
          link: "https://www.google.com.vn/?hl=vi",
        },
      ],
    };
  },

  methods: {
    submitData(note) {
      this.notes.unshift(note);
      alert("Note add!");
    },
  },
};
</script>

<style scoped></style>
