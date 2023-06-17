<template>
  <div class="container">
    <the-header></the-header>

    <create-note
      :title="title"
      :des="des"
      :link="link"
      
    ></create-note>

    <display-note 
    :title="title" 
    :des="des" 
    :link="link"
    @sendData="submitData"
    ></display-note>
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
      title: "",
      des: "",
      link: "",
    };
  },

  methods: {
    submitData(title, des, link) {
      this.title.push(title);
      this.des.push(des);
      this.link.push(link);
      alert("Note add!");
    },
  },
};
</script>

<style scoped></style>
