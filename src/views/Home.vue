<template>
  <div id="app">
    <Employees v-bind:employees="results" />
  </div>
</template>

<script>
import Employees from "../components/Employees";
import axios from "axios";
export default {
  name: "Home",
  components: {
    Employees,
  },
  data() {
    return {
      results: [],
    };
  },

  created() {
    axios
      .all([
        axios.get("https://next.json-generator.com/api/json/get/VJmA3f2KY"),
        axios.get("https://randomuser.me/api/?results=6"),
      ])
      .then(
        axios.spread((obj1, obj2) => {
          this.results = obj1.data;
          this.results1 = obj2.data.results;
          let pictureSwap = () => {
            for (let i = 0; i < this.results.length; i++) {
              this.results[i]["picture"] = this.results1[i]["picture"]["large"];
            }
          };
          pictureSwap();
        })
      );
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>