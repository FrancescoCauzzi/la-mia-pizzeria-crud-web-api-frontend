<script>
import axios from "axios";

export default {
  name: "Index",

  data() {
    return {};
  },
  created() {
    this.getPizzas();
  },
  methods: {
    getPizzas() {
      axios
        .get("https://localhost:7249/api/Pizzas/GetPizzas")
        .then((response) => {
          if (response.data.success) {
            console.log(response.data);
          } else {
            console.log("We did not find any pizza");
          }
        })
        .catch((error) => {
          console.error(error);
        });
    },
  },
};
</script>

<template>
  <div class="__red">
    <h1 class="__blue">This is my front end</h1>
  </div>
</template>

<style lang="scss" scoped>
.__red {
  background-color: red;
  .__blue {
    color: blue;
  }
}
</style>
