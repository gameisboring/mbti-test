<template>
  <div class="progress-wrapper">
    <div class="page">{{ page }} / {{ maxLength }}</div>
    <div
      class="gauge"
      :style="{
        width: `${(page / maxLength) * 300}px`,
        transition: `all 0.5s`,
      }"
    ></div>
  </div>
</template>
<script>
export default {
  computed: {
    page() {
      return this.$store.state.page;
    },
    maxLength() {
      return this.$store.state.questions.length;
    },
  },
};
</script>
<style scoped>
.progressbar {
  margin: 20px 0;
}

.page {
  font-size: 14px;
  margin-bottom: 10px;
}

.gauge {
  background-color: cornflowerblue;
  height: 5px;
  border-radius: 2.5px;
}

.progress-wrapper {
  width: 300px;
  margin: 0 auto;
}
</style>
