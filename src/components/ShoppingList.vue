<template>
  <section id="shopping-app">
    <div class="shopping-app">
      <div class="container-text">
        <div class="text">
          <h1>Shopping List</h1>

          <span><i class="fa fa-shopping-basket icon-font" aria-hidden="true"></i></span>
        </div>
      </div>
      <div class="fruits">
        <ul>
          <li v-for="(list, index) in lists" :key="index">
            {{ list }}
            <i
              class="fa fa-trash icon-mouse"
              aria-hidden="true"
              v-on:click="removeList(index)"
            ></i>
          </li>
        </ul>
      </div>
      <div class="container">
        <input
          type="text"
          placeholder="Create list"
          v-model="currentList"
          v-on:keyup.enter="addList"
        />
        <span><i class="fa fa-plus" aria-hidden="true"></i></span>
      </div>
      <p class="footer">Made With ❤ ❤ ❤ By Emilson</p>
    </div>
  </section>
</template>

<script>
export default {
  name: "ShoppingList",
  data() {
    return {
      lists: ["Surface Laptop 2", "Google Pixel", "Sony 1000xm4"],
      currentList: "",
    };
  },
  methods: {
    addList() {
      this.lists.push(this.currentList);
      this.currentList = "";
    },
    removeList(index) {
      this.lists.splice(index, 1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#shopping-app {
  display: flex;
  justify-content: center;
}

.fa-plus {
  background-color: #fca954;
  color: #ffffff;
  width: 40px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 30px;
}
.icon-font{
  font-size:40px;
  color: #fca954;
}
.icon-font:hover{
  
  transition: all 0.3s ease-in-out;
}

.btn {
  color: green;
}
.fruits {
  width: 300px;
  /* border: 1px solid black; */
  display: flex;
  flex-direction: column;
  padding: 20px;
  background: #444444;
}

.container {
  width: 300px;
  /* border: 1px solid black; */
  display: flex;
  /* flex-direction: column; */
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  margin: 10px 0px;
  background: #444444;
  color: #aaaaaa;
}

.container input {
  width: 80%;
  padding: 8px 0px;
  outline: none;
  background: transparent;
  border: none;
  color: #aaaaaa;
  font-size: 17px;
}

::placeholder {
  color: #aaaaaa;
}

.container-text {
  width: 300px;
  /* border: 1px solid black; */
  padding: 20px;
  margin: 20px 0px;
  background: #444444;
  color: #aaaaaa;
}
.text {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

li {
  margin: 20px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #aaaaaa;
}
.footer {
  color: #aaaaaa;
  padding: 10px 0px;
  text-align: center;
}
.icon-mouse {
  cursor: pointer;
}

@media (max-width: 332px) {
  .fruits,
  .container-text,
  .container {
    width: 270px;
    max-width: 250px;
  }
}
</style>
