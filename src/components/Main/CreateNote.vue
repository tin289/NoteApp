<template>
  <div class="container">
    <button class="create-button" @click="createNote">
      <img src="../../assets/style/icon/plus.png" alt="createNote" />
    </button>

    <teleport to="body">
      <div class="background"></div>

      <dialog open v-if="note">
        <header>
          <h2>What do you want to note?</h2>
        </header>

        <form>
          <div class="form-control">
            <label for="title">Title</label>
            <input
              id="title"
              name="title"
              type="text"
              v-model="createTitle"
            />
          </div>

          <div class="form-control">
            <label for="description">Description</label>
            <textarea
              id="description"
              name="description"
              type="text"
              rows="3"
              v-model="createDes"
            ></textarea>
          </div>

          <div class="form-control">
            <label for="link">Link</label>
            <input
              id="link"
              name="link"
              type="url"
              v-model="createLink"
            />
          </div>
        </form>

        <menu>
          <button class="cancel" @click="cancelCreate">Cancel</button>
          <button class="submit" @click="submitData">Submit</button>
        </menu>
      </dialog>
    </teleport>
  </div>
</template>

<script>
export default {
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
      note: false,
      createTitle: this.title,
      createDes:this.des,
      createLink: this.link,
    };
  },


  methods: {
    submitData() {
      if (this.createTitle.length > 0 && this.createDes.length > 0) {
        const showTitle = this.createTitle
        const showDes = this.createDes
        const showLink = this.createLink

        this.$emit('sendData', {
          showTitle,
          showDes,
          showLink
        })

        //clean
        this.createTitle = ''
        this.createDes = ''
        this.createLink = ''
        this.note = false
      } 
    },

    createNote() {
      this.note = true;
    },

    cancelCreate() {
      this.note = !this.note;
    },
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin: 20px 0 5px 0;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 10px 10px;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #f7ebff;
  background-color: rgb(252, 239, 241);
}

header {
  width: 100%;
  padding: 10px;
}

header h2 {
  margin: 0;
}

menu {
  padding: 1rem;
  display: flex;
  justify-content: flex-end;
  margin: 0;
}

@media (min-width: 768px) {
  dialog {
    left: calc(50%-20rem);
    width: 40rem;
  }
}

.submit {
  border: none;
  background: rgb(136, 221, 255);
  padding: 5px 15px;
  border-radius: 5px 5px;
  color: white;
  margin-left: 15px;
}

.cancel {
  border: none;
  background: rgb(251, 191, 121);
  padding: 5px 15px;
  border-radius: 5px 5px;
  color: white;
}

.submit:hover,
.cancel:hover {
  cursor: pointer;
  opacity: 0.8;
}

dialog {
  border-radius: 15px 15px;
  position: fixed;
  z-index: 100;
  border: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  overflow: hidden;
  top: 15%;
}

.background {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.139);
  z-index: 10000;
  display: none;
}

.create-button img {
  width: 40px;
}

.create-button {
  border-style: none;
  background-color: white;
  position: fixed;
  left: 95%;
  top: 90%;
}

.create-button:hover {
  cursor: pointer;
}
</style>
