<template>
  <div class="container">
    <div class="Card">
      <div class="card__main">
        <p>{{ info.setup }}</p>
        <h3>{{ info.punchline }}</h3>
        <div>
          <button @click="handleClick">Reload☄️</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "RandomWord",
  data() {
    return {
      info: {},
    };
  },
  mounted() {
    this.getRandomJoke();
  },
  methods: {
    handleClick() {
      window.location.reload();
      console.log("test");
    },
    async getRandomJoke() {
      await axios
        .get("https://official-joke-api.appspot.com/random_joke")
        .then((response) => {
          console.log("res: ", response.data);
          this.info = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  font-weight: bold;
}
p {
  font-weight: 500;
  font-size: 28px;
  text-align: "end";
}
.Card {
  display: flex;
  align-items: center;
  justify-content: center;
}
.card__main {
  background: white;
  padding: 12px 26px;
  width: 500px;
  height: 250px;
  border-radius: 8px;
  text-align: end;
  justify-content: end;
}
button {
  background: tomato !important;
  border: none;
  border-radius: 6px;
  color: white;
  padding: 8px;
}
</style>
