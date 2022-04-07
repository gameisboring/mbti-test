<template>
  <div class="flex flex-col justify-center">
    <h1>{{ page }}. {{ question }}</h1>
    <ButtonNew
      v-for="(item, index) in answers"
      styleType="pink"
      :key="index"
      :text="item.text"
      :clickEvent="
        () => {
          clickButton(item);
        }
      "
    />
    <Progress />
  </div>
</template>
<script>
export default {
  computed: {
    /* questions() {
      return this.$store.state.questions;
    },
    page() {
      return this.$store.state.page;
    }, */
    page() {
      return this.$store.state.page;
    },
    question() {
      return this.$store.state.questions[this.$store.state.page - 1].q;
    },
    answers() {
      return this.$store.state.questions[this.$store.state.page - 1].a;
    },
  },
  methods: {
    clickButton(item) {
      this.$store.dispatch("clickButton", item.value);
      if (this.page === this.$store.state.questions.length + 1) {
        const result = this.$store.state.result;
        console.log(result);
        this.$router.push({
          name: "result-mbti",
          params: {
            mbti: `${result.e ? "e" : "i"}${result.s ? "s" : "n"}${
              result.t ? "t" : "f"
            }${result.p ? "p" : "j"}`,
          },
        });
      }
    },
  },
};
</script>
<style></style>
