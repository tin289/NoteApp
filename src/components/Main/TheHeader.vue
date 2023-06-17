<template>
  <div class="container">
    <div class="header-category">
      <button class="header-category-button">
        <img src="../../assets/style/icon/notes.png" alt="note" />
        Note App
      </button>
      <button>Card</button>
      <button>Note</button>
      <button>Lunch Today</button>
      <button>Author</button>
    </div>

    <div class="header-user">
      <div class="header-welcome">
        <img src="../../assets/style/icon/user.png" alt="user" />
        <p>Welcome</p>
      </div>

      <div class="header-log-out">
        <button>
          <img src="../../assets/style/icon/logout.png" alt="log-out" />
          Log Out
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
img {
  width: 30px;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(81, 248, 248);
  height: 70px;
}

.header-category {
  display: flex;
}

.header-category button {
  margin: 0 20px 0 0;
  border-style: none;
  font-size: 20px;
  background-color: rgb(81, 248, 248);
  color: white;
  font-weight: 700;
  height: 70px;
}

.header-category-button {
  display: flex;
  align-items: center;
}

.header-category-button img {
  margin: 0 10px 0 10px;
}

button:hover {
  cursor: pointer;
  opacity: 0.8;
}

.header-user {
    display: flex;
    align-items: center;
}

.header-welcome {
    display: flex;
    align-items: center;
    margin: 0 50px 0 0;
    color: white;
    font-weight: 700;
}

.header-welcome img {
    width: 35px;
    height: 35px;
    margin-right: 10px;
}

.header-log-out button {
    display: flex;
    align-items: center;
    margin-right: 15px;
    background-color: rgb(253, 170, 76);
    color: white;
    border-style: none;
    height: 40px;
    font-weight: 700;
    padding: 20px;
    border-radius: 5px 5px;
}

.header-log-out button img {
    margin-right: 15px;
}
</style>
