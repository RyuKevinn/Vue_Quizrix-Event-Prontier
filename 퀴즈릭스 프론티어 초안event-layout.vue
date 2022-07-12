<template>
  <div class="event">
    <div class="w-full bg-black flex justify-center">
      <div class="w-[1000px] h-14 flex justify-between items-center">
        <div>
          <img class="w-[100px]" src="img/logo.png" alt="퀴즈릭스 로고" />
        </div>
        <div class="space-x-5">
          <a
            href="https://quizrix.com/"
            class="text-white text-sm hover:text-[#ffe400]"
            >퀴즈릭스</a
          >
          <a
            href="http://codnut.com/?page_id=16"
            class="text-white text-sm hover:text-[#ffe400]"
            >코드넛 회사소개</a
          >
          <button
            class="w-[100px] text-sm bg-[#ffe400] py-0.5 rounded-full hover:bg-white hover:text-black"
          >
            신청하기
          </button>
        </div>
      </div>
    </div>
    <main class="event-body-wrap">
      <div class="container">
        <nuxt />
      </div>
    </main>
    <div class="w-full bg-black flex justify-center">
      <div
        class="w-[1000px] h-12 flex justify-center items-center text-white text-xs"
      >
        (주)코드넛 ㅣ 홈페이지 : www.codnut.com ㅣ www.quizrix.com 이메일 :
        gorae@codnut.com ㅣ 전화 010 2854 9601
        <br />
        본사 : 충청북도 청주시 흥덕구 가경동 1361, 201호 / 서울사업소 : 서울시
        강남구 논현동 63-10 201호
      </div>
    </div>
  </div>
</template>
<script>
export default {
  head: {
    script: [
      {
        src: "https://cdn.tailwindcss.com"
      }
    ]
  },
  methods: {
    changePage(path) {
      this.$router.push({ path })
    }
  }
}
</script>
