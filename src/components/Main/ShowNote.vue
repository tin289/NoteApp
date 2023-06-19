<template>
  <div class="container">
    <div class="note-show">
      <div class="note">
        <header>
          <h3>{{ noteDisplay.title }}</h3>
          <div class="note-icon">
            <button>
              <img src="../../assets/style/icon/edit.png" alt="edit" />
            </button>
            <button @click="DeleteNote(noteDisplay)">
              <img src="../../assets/style/icon/delete.png" alt="delete"/>
            </button>
          </div>
        </header>

        <div class="note-detail">
          <h3>Detail</h3>
          <p>{{ noteDisplay.des }} </p>
        </div>

        <div class="note-link">
          <a :href="noteDisplay.link" target="_bank">Click here</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: ['noteDisplay'],

  methods: {
    DeleteNote(note) {
      this.$emit('noteDelete', note)
    }
  }

};
</script>

<style scoped>
.note-show {
  display: flex;
  justify-content: space-around;
}

img {
  width: 30px;
}

.note {
  border: 4px solid #ccc;
  border-radius: 10px 10px;
  padding: 10px 20px;
  width: 30%;
  margin: 20px 0;
  
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 25px;
}

.note-icon button {
    margin-left: 15px;
    border-style: none;
    background-color: transparent;
}

.note-icon button:hover {
    cursor: pointer;
    opacity: 0.5;
}

.note-detail h3 {
  margin-bottom: 10px;
}

.note-detail p {
  margin-top: 0;
}

.note-link a {
  text-decoration: none;
  color: coral;
}

.note-link a:hover,
.note-link a:focus {
  cursor: pointer;
  opacity: 0.5;
}

.note-link a:active {
  color: violet;
}
</style>
