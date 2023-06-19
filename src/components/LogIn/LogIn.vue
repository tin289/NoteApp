<template>
  <div class="container">
    <input
      type="text"
      placeholder="Pls enter your name"
      v-model="name"
      @keydown.enter="startNote"
    />
    <button @click="startNote">Log In</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            name: ''
        }
    },

    methods: {
        startNote() {
            if (this.name.length === 0) {
                alert('Pls enter your name')
            }
            else {
                this.$emit('startNote')
            }
        }
    }
};
</script>

<style scoped>
.container {
  text-align: center;
  padding: 30px;
  margin: 300px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 12px;
  width: 100%;
  max-width: 60rem;
}

input {
  font: inherit;
  border: 1px solid #ccc;
  padding: 1rem 2rem;
  border-radius: 12px;
  margin: 1rem;
  width: 20rem;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

input:focus {
  outline: none;
  border-color: #e696dd;
  background-color: pink;
}

button {
  font: inherit;
  border: 1px solid #54b0e4;
  background-color: #54b0e4;
  color: white;
  padding: 1rem 2rem;
  border-radius: 12px;
  margin: 1rem;
  width: 12rem;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
  cursor: pointer;
}

button:focus {
  outline: none;
}

button:hover,
button:active {
  opacity: 0.8;
  box-shadow: 1px 1px 8px rgba(0, 0, 0, 0.26);
}
</style>
