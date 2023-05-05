<script >
import Card from "./components/Card.Vue"

export default {
  components: {
    Card
  },
  //資料區
  data() {
    return {
      a: 1,
      temp: 0,
      person: {
        name: "John",
        age: 23,
      },
      arr: [1, 2, 3, 4, 5],
      arrMeal: "",
      isShow: true
    }
  },
  //方法區
  methods: {
    fn() {
      console.log("這是fn");
    },

    test() {
      //.....
    },
    changeAValue() {
      this.a = this.temp;
    },
    switch123() {
      console.log("switch!");
      this.isShow = !this.isShow;
    }

  },
  //生命週期區
  mounted() {
    this.fn();
    console.log(this.person.name);

    //測試直接修改資料區的變數
    // setTimeout(() => {
    //   this.a = 50000;
    //   this.container.innerHTML+=`<p>123</p>`
    // }, 2000);

  },
}
</script>

<template>
  <header>
    <!-- <h1>Vue指令-for</h1>
    <p>a : {{ a }}</p>
    
    <p>V-for</p>
    <ul>
      <li v-for="item in arr">{{ item }}</li>
    </ul> -->


  </header>
  <div class="container">
    <Card />
    <Card />
    <Card />
    <!-- <Card v-for="a in [3, 3, 3, 3, 3]" /> -->
  </div>
  <!-- <div class="text-area">
    <h1>V-Model</h1>
    <h2>a = {{ a }}</h2>
    <p>temp:{{ temp }}</p>
    <input type="text" v-model="temp">
    <button class="btn" v-on:click="changeAValue">update</button>
    <h1>V-on</h1>
  </div> -->
  <div class="meal-area">
    <h1>V-model</h1>
    <label for="breakfast">breakfast</label>
    <input type="radio" id="breakfast" v-model="arrMeal" value="breakfast">
    <label for="lunch">lunch</label>
    <input type="radio" id="lunch" v-model="arrMeal" value="lunch">
    <label for="dinner">dinner</label>
    <input type="radio" id="dinner" v-model="arrMeal" value="dinner">
    <p>你選擇了：{{ arrMeal }}</p>
  </div>
  <div class="box-area d-flex">
    <!-- <button v-on:click="switch123">switch</button>
    <div v-if="isShow" class="box bg-primary">
      <h1>box</h1>

    </div>
    <div v-if="isShow" class="box bg-secondary">
      <h1>box</h1>

    </div> -->
    <ul>
      <li v-if="arrMeal == 'breakfast'">早餐</li>
      <li v-else-if="arrMeal == 'lunch'">五餐</li>
      <li v-else-if="arrMeal == 'dinner'">晚餐</li>
    </ul>
  </div>
</template>

<style scoped>
.container {
  display: flex;
}

.text-area {
  text-align: center;
}

.box {
  width: 16rem;
  height: 16rem;

}
</style>
