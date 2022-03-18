<template>
  <div>
    <h1>{{ myTitle }}</h1>
    <input type="email" ref="Email" />
    <button type="button" class="btn btn-outline-primary" @click="handleClick">
      Check Email ID
    </button>
    <button type="reset" @click="resetInput">Reset</button>
    <h2>{{ message }}</h2>
  </div>
</template>

 <script>
import HelloWorld from "./components/HelloWorld";

export default {
  // name: "App2",
  // root component and sub compoenet need to mount on APP , Name is optional
  data() {
    return {
      myTitle: "This is my first Vue js to build application",
      message: "",
    };
  },
  methods: {
    resetInput() {
      this.$refs.Email.value = " ";
      this.message = "";
    },
    handleClick() {
      console.log("email id " + this.$refs.Email.value);
      if (
        String(this.$refs.Email.value)
          .toLowerCase()
          .match(
            /^(([^<>()\[\]\.,;:\s@\"]+(\.[^<>()\[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()\.,;\s@\"]+\.{0,1})+[^<>()\.,;:\s@\"]{2,})$/
          )
      ) {
        this.message =
          " " + String(this.$refs.Email.value) + " is correct Email ID ";
      } else {
        this.message =
          " " + String(this.$refs.Email.value) + " is in correct  Email ID ";
      }
    },
  },

  // components: {
  //   HelloWorld
  // }
};
</script>
 
// this styles are global scoppped 
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  font-size: 20px;
  text-decoration: underline;
  color: aqua;
  border: 2px solid red;
}
</style>
