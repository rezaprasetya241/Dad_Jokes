<template>
  <div class="home">
    <RandomWord />
  </div>
</template>

<script>
// @ is an alias to /src
import RandomWord from "@/components/RandomWord.vue";

export default {
  name: "HomeView",
  components: {
    RandomWord,
  },
};
</script>
