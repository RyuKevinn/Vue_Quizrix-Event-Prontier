<template>
  <div class="event-container">
    <div class="event-title">
      <span>퀴즈릭스와 함께하는</span>
    </div>
    <div class="event-article">
      <h1>2022년 에듀테크 프론티어 모집</h1>
      <div class="article-ment">
        <p>
          디지털 문제집 출판플랫폼 퀴즈릭스와 함께 성장할 "에듀테크 프론티어" 를
          모집합니다. "에듀테크 프론티어" 는 빠르게 변화하는 교육 환경에서
          디지털 교재/ 문제집을 만들어보고 현장에 적용해보고자하는 누구나 참여할
          수 있습니다.
        </p>
        <p>
          퀴즈릭스 quizrix.com 는 교육업계를 혁신하고자 하는 대한민국 스타트업
          코드넛의 서비스입니다.
        </p>
      </div>
      <div class="article-video">
        <iframe
          width="100%"
          height="230"
          frameborder="0"
          allowfullscreen
          :src="parserUrl"
        ></iframe>
      </div>
      <div class="article-info">
        <table>
          <colgroup>
            <col class="info-name" />
            <col class="info-title" />
          </colgroup>
          <tbody>
            <tr>
              <td><strong>기간</strong></td>
              <td>2022년 7월 15일부터 8월 30일 까지 (약 40일간 활동)</td>
            </tr>
            <tr>
              <td><strong>활동내용</strong></td>
              <td>
                <p>
                  (필수) 에듀테크 프론티어 밋업 참석 (7월 16일, 8월 13일 2회)
                </p>
                <p>문제집 플랫폼 퀴즈릭스에 문제집 생성 및 문제 출제</p>
                <p>제작한 문제집을 이메일 또는 카카오톡을 통해 공유</p>
                <p>설문조사 및 FGI 참여</p>
                <p>(선택) 블로그에 사용소감 및 후기 작성</p>
              </td>
            </tr>
            <tr>
              <td><strong>활동비</strong></td>
              <td>
                <p>기본 활동비 40만원 + 문제집 제작비 (문항별 5,000원 내외)</p>
                <p>(임금 형태로 지급하나 상품권 등으로 대체 가능)</p>
                <p>우수활동 인센티브 지급</p>
              </td>
            </tr>
            <tr>
              <td><strong>대상</strong></td>
              <td>
                <p>
                  에듀테크와 디지털 교재에 관심이 있는 누구나 (15명 내외 선발
                  예정)
                </p>
                <p>교육 관련 종사자 및 관련학과 학생우대</p>
              </td>
            </tr>
          </tbody>
        </table>
        <button class="event-regist-btn" @click="changePage('/event/regist')">
          신청하기
        </button>
      </div>
      <div class="article-guide">
        <h3 class="guide-title">디지털 문제집 제작가이드</h3>
        <div class="guide-text">
          <ol>
            <li>
              제작된 문제집은 클라우드 문제집출판플랫폼 퀴즈릭스 (quizrix.com)
              에 12개월 이상 유지하여야 합니다.
            </li>
            <li>
              저작도구를 활용하여 10문항 이상으로 제작된 문제집을 제작하여
              타인의 저작권을 침해해서는 안됩니다.
            </li>
            <li>
              <p>
                밋업과 세미나를 통해 각 1편의 문제집을 제작하셔야 추가적으로
                문제집을 제작하실 수 있습니다.
              </p>
              <p>
                추가 제작시 문항당 5,000원의 활동비를 최대 60만원까지
                지급합니다.
              </p>
            </li>
            <li>
              추가 문제집 제작 시 콘텐츠 매니저와 관련 협의를 진행할 수
              있습니다.
            </li>
            <li>
              제작된 문제집은 학생들에게 배포하는 것을 권장드립니다. (5명 내외)
            </li>
          </ol>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import MediaMixin from "../../Viewer/mixins/media-mixins"

export default {
  name: "EventMainComponent",
  mixins: [MediaMixin],
  head: {
    script: [
      {
        src: "https://cdn.tailwindcss.com"
      }
    ]
  },
  data() {
    return {
      parserUrl: "",
      insert: "https://www.youtube.com/embed/90gDoUgEFNE?controls=0"
    }
  },
  mounted() {
    let mediaInfo = this.setMedia(this.insert)
    this.parserUrl = mediaInfo.parserUrl
  },
  methods: {
    changePage(path) {
      this.$router.push({ path })
    }
  }
}
</script>
<style lang="scss">
@import "@/assets/scss/event.scss";
</style>
