<template>
  <section id="shopping-app">
<div class="shopping-app">
          <div class="container-text">
                <div class="text">

                    <h1>Shopping List</h1>
                    
                    <span><i class="fa fa-plus" aria-hidden="true"></i></span>
                
                </div>
                
            </div>
            <div class="fruits">
                <ul>
                    <li v-for="(fruit, index) in fruits" :key="index">
                        {{ fruit }}
				<!-- <button class="btn " > -->
				<i class="fa fa-trash" aria-hidden="true" v-on:click="removeFruit(index)"></i>
                <!-- <i class="fa fa-thumb-tack" aria-hidden="true"></i> -->
				<!-- </button>    -->
                    </li>
                </ul>
            </div>
            <div class="container">
                <input type="text" v-model="currentFruit" v-on:keyup.enter="addFruit" />
                <span><i class="fa fa-plus" aria-hidden="true"></i></span>
            </div>
</div>
</section>
</template>

<script>
export default {
  name: "ShoppingList",
  //   props: {
  //     msg: String
  //   }
  data() {
    return {
      fruits: ["apple", "oranges", "apricots"],
      currentFruit: ""
    };
  },
  methods: {
    addFruit() {
      this.fruits.push(this.currentFruit);
      this.currentFruit = "";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#shopping-app {
  display: flex;
  justify-content: center;
}

.fa-plus{
background-color:#FCA954;
color:#ffffff;
width:40px;
height:40px;
display:flex;
justify-content:center;
align-items:center;
border-radius:30px
}

.btn{color: green}
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
  color: #AAAAAA;
}

.container input {
  width: 80%;
  padding: 8px 0px;
outline:none;
background:transparent;
border:none;
color: #AAAAAA;
font-size:17px;
}

.container-text {
  width: 300px;
  /* border: 1px solid black; */
  padding: 20px;
  margin: 20px 0px;
  background: #444444;
  color: #AAAAAA;
}
.text{
 display: flex;
  align-items: center;
justify-content: space-between;
}

li {
  margin: 20px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
 color: #AAAAAA;
}

@media(max-width:332px){
.fruits,.container-text,.container{
width:270px;
max-width:250px;

}
}
</style>
