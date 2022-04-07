<template>
  <!-- 인트로 페이지 -->
  <main v-if="page === 0">
    <img
      src="https://w.namu.la/s/222a5002a6c2fa55715b0d7f6dff9619803003ed3800ae98f5379144359473fef95d794c47d2f8cf70dd641035d1eb14f1bbeab1209d6800e247f35838cb39ed0a27f8229d165394f0b50233f7517f48c8249dd061399446bfc2fd43747452d3"
      alt="단국대로고"
    />
    <h1>나와 비슷한 유형 찾기</h1>
    <h2>나와 닮은 @@@은 누구일까요?</h2>
    <Button text="테스트 시작" styleType="blue" :clickEvent="startTest" />
  </main>
  <!-- 질문 페이지 -->
  <main v-else-if="page < 5">
    <Question />
  </main>
  <!-- 결과 페이지
  <main v-else-if="page === 9">
    <Result />
  </main> -->
</template>

<script>
export default {
  computed: {
    page() {
      return this.$store.state.page;
    },
  },
  methods: {
    startTest() {
      this.$store.commit("SET_PAGE", 1);
    },
  },
};

/* 메인 페이지 안에 들어갈 것
   1. 인트로 페이지
   2. 조건부 렌더링을 통해 퀴즈 컴포넌트
   3. 결과는 페이지 이동 /result/_mbti
*/
</script>
<style></style>
