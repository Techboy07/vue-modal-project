<template>
  <p>Reaction time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    const myScore = this.score;
    if (myScore < 250) {
      this.rank = "Ninja fingers";
    } else if (myScore < 400) {
      this.rank = "Rapid  Reflexes";
    } else {
      this.rank = "Snails pace...";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: #0faf87;
  font-weight: bold;
}
</style>
