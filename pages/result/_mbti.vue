<template>
  <main>
    <img :src="result[mbti].img" :alt="result[mbti]" />
    <h1>{{ result[mbti].title }}</h1>
    <p v-html="result[mbti].desc"></p>
    <ButtonNew text="다시 테스트하기!" :clickEvent="resetPage" />
  </main>
</template>
<script>
export default {
  data() {
    return {
      mbti: null,
      result: {
        istj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/sentinels_Logistician_ISTJ_introduction.svg?v=1",
          title: "청렴결백한 논리주의자, 세상의 소금형",
          desc: "논리주의자형은 가장 다수의 사람이 속하는 성격 유형으로 인구의 대략 13%를 차지합니다. 청렴결백하면서도 실용적인 논리력과 헌신적으로 임무를 수행하는 성격으로 묘사되기도 하는 이들은, 가정 내에서뿐 아니라 법률 회사나 법 규제 기관 혹은 군대와 같이 전통이나 질서를 중시하는 조직에서 핵심 구성원 역할을 합니다. 이 유형의 사람은 자신이 맡은 바 책임을 다하며 그들이 하는 일에 큰 자부심을 가지고 있습니다. 또한, 목표를 달성하기 위해 시간과 에너지를 허투루 쓰지 않으며, 이에 필요한 업무를 정확하고 신중하게 처리합니다.",
        },
        istp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/explorers_Virtuoso_ISTP_introduction.svg?v=1",
          title: "논리적인 실용주의자, 백과사전형",
          desc: "냉철한 이성주의적 성향과 왕성한 호기심을 가진 만능재주꾼형 사람은 직접 손으로 만지고 눈으로 보면서 주변 세상을 탐색하는 것을 좋아합니다. 무엇을 만드는 데 타고난 재능을 가진 이들은 하나가 완성되면 또 다른 과제로 옮겨 다니는 등 실생활에 유용하면서도 자질구레한 것들을 취미 삼아 만드는 것을 좋아하는데, 그러면서 새로운 기술을 하나하나 터득해 나갑니다. 종종 기술자나 엔지니어이기도 한 이들에게 있어 소매를 걷어붙이고 작업에 뛰어들어 직접 분해하고 조립할 때보다 세상에 즐거운 일이 또 없을 것입니다. 전보다 조금은 더 향상된 모습으로요.",
        },
        isfj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/sentinels_Defender_ISFJ_introduction.svg?v=1",
          title: "용감한 수호자, 실용적인 조력가",
          desc: "수호자형 사람은 꽤 독특한 특징을 가지고 있는데, 이 유형에 속하는 사람은 이들을 정의하는 성격 특성에 꼭 들어맞지 않는다는 점입니다. 타인을 향한 연민이나 동정심이 있으면서도 가족이나 친구를 보호해야 할 때는 가차 없는 모습을 보이기도 합니다. 조용하고 내성적인 반면 관계술에 뛰어나 인간관계를 잘 만들어갑니다. 안정적인 삶을 지향하지만 이들이 이해받고 존경받는다고 생각되는 한에서는 변화를 잘 수용합니다. 이처럼 수호자형 사람은 한마디로 정의 내리기 힘든 다양한 성향을 내포하고 있는데, 이는 오히려 그들의 장점을 승화시켜 그들 자신을 더욱 돋보이게 합니다.",
        },
        isfp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/explorers_Adventurer_ISFP_introduction.svg?v=1",
          title: "호기심 많은 예술가, 성인군자형",
          desc: '모험가형 사람은 일반적으로 사람들이 생각하듯 야외에서 앙증맞은 나무 그림을 그리고 있는 그런 유형의 예술가는 아니지만, 진정한 예술가라고 할 수 있습니다. 실상 상당수 많은 이들이 그러한 능력을 충분히 갖추고 있기도 합니다. 이들은 그들의 심미안이나 디자인 감각, 심지어는 그들의 선택이나 행위를 통하여 사회적 관습이라는 한계를 뛰어넘고자 합니다. 실험적인 아름다움이나 행위를 통해 전통적으로 기대되는 행동양식이나 관습에 도전장을 내미는 이들은 "저를 가두어두려 하지 마세요!"라고 수없이 외칩니다.',
        },
        intj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/analysts_Architect_INTJ_introduction.svg?v=1",
          title: "용의주도한 전략가",
          desc: "윗자리에 있는 사람은 고독한 법, 전략적 사고에 뛰어나며 매우 극소수인 건축가형 사람은 이를 누구보다 뼈저리게 이해합니다. 전체 인구의 2%에 해당하는 이들은 유독 여성에게서는 더욱 찾아보기 힘든 유형으로, 인구의 단 0.8%를 차지합니다. 체스를 두는 듯한 정확하고 계산된 움직임과 풍부한 지식을 소유하고 있는 이들은 그들과 견줄 만한 비슷한 부류의 사람을 찾는 데 종종 어려움을 겪습니다. 건축가형 사람은 상상력이 풍부하면서도 결단력이 있으며, 야망이 있지만 대외적으로 표현하지 않으며, 놀랄 만큼 호기심이 많지만 쓸데없는 데 에너지를 낭비하는 법이 없습니다.",
        },
        intp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/analysts_Logician_INTP_introduction.svg?v=1",
          title: "논리적인 사색가, 아이디어 뱅크형",
          desc: "사색가형은 전체 인구의 3% 정도를 차지하는 꽤 흔치 않은 성격 유형으로, 이는 그들 자신도 매우 반기는 일입니다. 왜냐하면, 사색가형 사람보다 '평범함'을 거부하는 이들이 또 없기 때문입니다. 이 유형의 사람은 그들이 가진 독창성과 창의력, 그리고 그들만의 독특한 관점과 왕성한 지적 호기심에 나름의 자부심을 가지고 있습니다. 보통 철학자나 사색가, 혹은 몽상에 빠진 천재 교수로도 많이 알려진 이들은 역사적으로 수많은 과학적 발전을 이끌어 내기도 하였습니다.",
        },
        infj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/diplomats_Advocate_INFJ_introduction.svg?v=1",
          title: "통찰력 있는 선지자, 예언자형",
          desc: "선의의 옹호자형은 가장 흔치 않은 성격 유형으로 인구의 채 1%도 되지 않습니다. 그럼에도 불구하고 나름의 고유 성향으로 세상에서 그들만의 입지를 확고히 다집니다. 이들 안에는 깊이 내재한 이상향이나 도덕적 관념이 자리하고 있는데, 다른 외교형 사람과 다른 점은 이들은 단호함과 결단력이 있다는 것입니다. 바라는 이상향을 꿈꾸는데 절대 게으름 피우는 법이 없으며, 목적을 달성하고 지속적으로 긍정적인 영향을 미치고자 구체적으로 계획을 세워 이행해 나갑니다.",
        },
        infp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/diplomats_Mediator_INFP_introduction.svg?v=1",
          title: "열정적인 중재자, 잔 다르크형",
          desc: "이들은 논리나 단순한 흥미로움, 혹은 인생의 실용적인 부분이 아닌 그들 나름의 원리원칙에 근거하여 사고하고 행동합니다. 더욱이 성취에 따르는 보상이나 그렇지 못할 경우에 생길 수 있는 불이익 여부에 상관없이 순수한 의도로 인생의 아름다움이나 명예 그리고 도덕적 양심과 미덕을 좇으며 나름의 인생을 설계해 나갑니다. 그리고 그러한 본인들의 생각과 행동에 자부심을 느끼기도 하는데, 이는 마땅한 일입니다. 하지만 모든 사람이 그들의 생각 뒤에 숨은 동기나 의미를 정확히 파악하지는 못하는데, 이는 자칫 이들을 외톨이로 만들 수도 있습니다.",
        },
        esfj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/sentinels_Consul_ESFJ_introduction.svg?v=1",
          title: "사교적인 외교관, 친선도모형",
          desc: "동정심이 많고 다른 사람에게 관심을 쏟으며 인화를 중시한다. 타고난 협력자로서 동료애가 많고 친절하며 능동적인 구성원이다. 이야기 하기를 즐기며 정리정돈을 잘하고, 참을성이 많고 다른 사람들을 잘 도와준다. 사람을 다루고 행동을 요구하는 분야, 예를 들면 교직, 성직, 판매 특히 동정심을 필요로 하는 간호나 의료 분야에 적합하다. 일이나 사람 관련 문제에 대하여 냉철한 입장을 취하기 어려워한다. 반대 의견에 부딪혔을 때나, 자신의 요구가 거절 당했을 때 마음의 상처를 받는다.",
        },
        estj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/sentinels_Executive_ESTJ_introduction.svg?v=1",
          title: "엄격한 관리자, 사업가형",
          desc: "관리자형 사람은 그들 생각에 반추하여 무엇이 옳고 그른지를 따져 사회나 가족을 하나로 단결시키기 위해 사회적으로 받아들여지는 통념이나 전통 등 필요한 질서를 정립하는 데 이바지하는 대표적인 유형입니다. 정직하고 헌신적이며 위풍당당한 이들은 비록 험난한 가시밭길이라도 조언을 통하여 그들이 옳다고 생각하는 길로 사람들을 인도합니다. 군중을 단결시키는 데에 일가견이 있기도 한 이들은 종종 사회에서 지역사회조직가와 같은 임무를 수행하며, 지역 사회 발전을 위한 축제나 행사에서부터 가족이나 사회를 하나로 결집하기 위한 사회 운동을 펼치는 데 사람들을 모으는 역할을 하기도 합니다.",
        },
        estp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/explorers_Entrepreneur_ESTP_introduction.svg?v=1",
          title: "모험을 즐기는 사업가, 수완 좋은 활동가형",
          desc: "주변에 지대한 영향을 주는 사업가형 사람은 여러 사람이 모인 행사에서 이 자리 저 자리 휙휙 옮겨 다니는 무리 중에서 어렵지 않게 찾아볼 수 있습니다. 직설적이면서도 친근한 농담으로 주변 사람을 웃게 만드는 이들은 주변의 이목을 끄는 것을 좋아합니다. 만일 관객 중 무대에 올라올 사람을 호명하는 경우, 이들은 제일 먼저 자발적으로 손을 들거나 아니면 쑥스러워하는 친구를 대신하여 망설임 없이 무대에 올라서기도 합니다.",
        },
        entp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/analysts_Debater_ENTP_introduction.svg?v=1",
          title: "뜨거운 논쟁을 즐기는 변론가, 발명가형",
          desc: "변론가형 사람은 타인이 믿는 이념이나 논쟁에 반향을 일으킴으로써 군중을 선동하는 일명 선의의 비판자입니다. 결단력 있는 성격 유형이 논쟁 안에 깊이 내재한 숨은 의미나 상대의 전략적 목표를 꼬집기 위해 논쟁을 벌인다고 한다면, 변론가형 사람은 단순히 재미를 이유로 비판을 일삼습니다. 아마도 이들보다 논쟁이나 정신적 고문을 즐기는 성격 유형은 없을 것입니다. 이는 천부적으로 재치 있는 입담과 풍부한 지식을 통해 논쟁의 중심에 있는 사안과 관련한 그들의 이념을 증명해 보일 수 있기 때문입니다.",
        },
        esfp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/explorers_Entertainer_ESFP_introduction.svg?v=1",
          title: "자유로운 영혼의 연예인, 사교적인 유형",
          desc: "천부적으로 스타성 기질을 타고난 이들은 그들에게 쏟아지는 스포트라이트를 즐기며 어디를 가나 모든 곳이 이들에게는 무대입니다. 사실상 많은 배우가 이 성격 유형에 속하기도 합니다. 간혹 친구나 다른 이들과 어울릴 시 쇼맨십에 찬 모습을 보이기도 하는데, 썰렁한 유머를 던져 주의를 집중시키기도 하는 이들은 그들이 가는 곳곳마다 시끌벅적한 파티를 연상케 합니다. 매우 사교적인 성향의 이들은 단순한 것을 좋아하며, 좋은 사람들과 어울려 즐거운 시간을 갖는 것보다 세상에 더 큰 즐거움은 없다고 여깁니다.",
        },
        enfp: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/diplomats_Campaigner_ENFP_introduction.svg?v=1",
          title: "재기발랄한 활동가, 스파크형",
          desc: "활동가형 사람은 자유로운 사고의 소유자입니다. 종종 분위기 메이커 역할을 하기도 하는 이들은 단순한 인생의 즐거움이나 그때그때 상황에서 주는 일시적인 만족이 아닌 타인과 사회적, 정서적으로 깊은 유대 관계를 맺음으로써 행복을 느낍니다. 매력적이며 독립적인 성격으로 활발하면서도 인정이 많은 이들은 인구의 대략 7%에 속하며, 어느 모임을 가든 어렵지 않게 만날 수 있습니다.",
        },
        entj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/analysts_Commander_ENTJ_introduction.svg?v=1",
          title: "대담한 통솔자, 지도자형",
          desc: "통솔자형 사람은 천성적으로 타고난 리더입니다. 이 유형에 속하는 사람은 넘치는 카리스마와 자신감으로 공통의 목표 실현을 위해 다른 이들을 이끌고 진두지휘합니다. 예민한 성격의 사회운동가형 사람과 달리 이들은 진취적인 생각과 결정력, 그리고 냉철한 판단력으로 그들이 세운 목표 달성을 위해 가끔은 무모하리만치 이성적 사고를 하는 것이 특징입니다. 이들이 인구의 단 3%에 지나지 않는 것이 어쩌면 다행일 수도 있습니다. 그렇지 않으면 인구 대다수를 차지하는 소심하고 섬세한 성향의 사람들이 모두 주눅 들어 살지도 모르니까요. 단, 평소 잊고 살기는 하나 우리 삶을 윤택하게 해주는 위대한 사업가나 기관을 이끄는 통솔자형 사람들이 있음에 다행이기도 합니다.",
        },
        enfj: {
          img: "https://static.neris-assets.com/images/personality-types/scenes/diplomats_Protagonist_ENFJ_introduction.svg?v=1",
          title: "정의로운 사회운동가, 언변능숙형",
          desc: "사회운동가형 사람은 카리스마와 충만한 열정을 지닌 타고난 리더형입니다. 인구의 대략 2%가 이 유형에 속하며, 정치가나 코치 혹은 교사와 같은 직군에서 흔히 볼 수 있습니다. 이들은 다른 이들로 하여금 그들의 꿈을 이루며, 선한 일을 통하여 세상에 빛과 소금이 될 수 있도록 사람들을 독려합니다. 또한, 자신뿐 아니라 더 나아가 살기 좋은 공동체를 만들기 위해 사람들을 동참시키고 이끄는 데에서 큰 자부심과 행복을 느낍니다.",
        },
      },
    };
  },
  created() {
    this.mbti = this.$route.params.mbti;

    // 예외처리
    if (this.result[this.$route.params.mbti] === undefined) {
      this.$router.push({ name: "index" });
    }
  },
  methods: {
    resetPage() {
      this.$store.dispatch("clickResetButton");
      this.$router.push({ name: "index" });
    },
  },
};
</script>
<style></style>
