<template>
  <div class="event-container">
    <div class="event-title">
      <span>퀴즈릭스와 함께하는</span>
    </div>
    <div class="event-article">
      <h1>2022년 에듀테크 프론티어 신청</h1>
      <div class="article-ment">
        <p>
          에듀테크 프론티어에 신청해주셔서 감사합니다. 기재해 주신 사항은
          에듀테크 프론티어 프로그램 운영에 참고로 사용하기 위한 자료로
          활용됩니다. 개인정보는 (주)코드넛에서 1년간 보관합니다.
        </p>
      </div>
      <div class="article-regist">
        <form @submit="onSubmit">
          <div class="regist-info">
            <h5 class="info-title">기본 정보</h5>
            <ul v-if="!isMobile">
              <li>
                <label for="name">이름</label>
                <input
                  type="text"
                  id="name"
                  v-model="registData.name.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="phone">핸드폰</label>
                <input
                  type="text"
                  id="phone"
                  v-model="registData.phone.str"
                  class="border-radius"
                />
                <label for="email">이메일</label>
                <input
                  type="text"
                  id="email"
                  v-model="registData.email.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="address">주소</label>
                <input
                  type="text"
                  id="address"
                  v-model="registData.address.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="party">소속/회사</label>
                <input
                  type="text"
                  id="party"
                  v-model="registData.party.str"
                  class="border-radius"
                />
                <span class="guide-ment"
                  >* 학생 일 경우 재학중인 학교/전공</span
                >
              </li>
            </ul>
            <ul v-else>
              <li>
                <label for="name">이름</label>
                <input
                  type="text"
                  id="name"
                  v-model="registData.name.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="phone">핸드폰</label>
                <input
                  type="text"
                  id="phone"
                  v-model="registData.phone.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="email">이메일</label>
                <input
                  type="text"
                  id="email"
                  v-model="registData.email.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="address">주소</label>
                <input
                  type="text"
                  id="address"
                  v-model="registData.address.str"
                  class="border-radius"
                />
              </li>
              <li>
                <label for="party">소속/회사</label>
                <input
                  type="text"
                  id="party"
                  v-model="registData.party.str"
                  class="border-radius"
                />
                <span class="guide-ment"
                  >* 학생 일 경우 재학중인 학교/전공</span
                >
              </li>
            </ul>
          </div>
          <div class="regist-add-info">
            <h5 class="info-title">부가 정보</h5>
            <ul>
              <li
                v-for="(bItems, bIndex) in addInfoData"
                :key="bIndex"
                class="add-info-box"
              >
                <p>{{ bItems.title }}</p>
                <div class="info-select">
                  <div
                    class="select-box"
                    v-for="(sItems, sIndex) in bItems.sel"
                    :key="sIndex"
                  >
                    <input
                      type="radio"
                      v-bind:value="sItems"
                      v-model="registData[bItems.model]"
                      :id="bItems.category + sIndex"
                    />
                    <label :for="bItems.category + sIndex">{{ sItems }}</label>
                  </div>
                </div>
              </li>
              <li class="add-info-box">
                <label for="explanation">
                  <p>3) 제작하고자 하는 문제집에 대해 간단하게 설명해주세요.</p>
                </label>
                <span class="guide-ment">
                  *문제집을 학습하는 대상, 과목, 과정 구성, 문항 수 및 분량,
                  배포계획, 타 플랫폼이나 학습영상 연계 등
                </span>
                <textarea
                  type="text"
                  id="explanation"
                  v-model="registData.explanation.str"
                  class="border-radius"
                />
              </li>
              <li class="add-info-box">
                <label for="introduce">
                  <p>
                    4) 귀하를 소개하거나 제작된 문제집/교재 등이 있다면 URL을
                    알려주세요.
                  </p>
                </label>
                <input
                  type="text"
                  id="introduce"
                  v-model="registData.introduce"
                  class="border-radius"
                />
              </li>
            </ul>
          </div>
          <div class="regist-submit">
            <button
              class="submit-cancle btn-radius"
              type="button"
              @click="changePage('/event')"
            >
              취소
            </button>
            <button type="submit" class="submit-agree btn-radius">
              개인정보제공 동의 및 신청하기
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ProntierRegistComponent",
  head: {
    script: [
      {
        src: "https://cdn.tailwindcss.com"
      }
    ]
  },
  data() {
    return {
      addInfoData: [
        {
          category: "selectDate",
          title: "1) 에듀테크 프론티어 밋업 참석가능날짜를 선택해주세요",
          sel: [
            "2022년 7월 16일 1차 밋업",
            "2022년 8월 13일 2차 밋업",
            "둘 다 가능",
            "둘 다 불가"
          ],
          model: "participation"
        },
        {
          category: "selectPurpose",
          title:
            "2) 에듀테크 프론티어 프로그램에서는 디지털 문제집을 만들게 됩니다. 만들고자하는 문제집 분야를 선택해주세요",
          sel: [
            "초등 분야",
            "중고등 분야",
            "취험, 수험서",
            "자격증, 전문 분야",
            "취미,유머 등 기타분야",
            "아직 결정하지 못함"
          ],
          model: "category"
        }
      ],
      registData: {
        name: {
          str: "",
          label: "이름"
        },
        phone: {
          str: "",
          label: "번호"
        },
        email: {
          str: "",
          label: "이메일"
        },
        address: {
          str: "",
          label: "주소"
        },
        party: {
          str: "",
          label: "소속/회사"
        },
        participation: "",
        category: "",
        explanation: {
          str: "",
          label: "제작 문제집 설명란"
        },
        introduce: ""
      },
      isMobile: false,
      nowWidth: 0
    }
  },
  mounted() {
    this.handleWidth()
    window.addEventListener("resize", this.handleWidth)
  },
  methods: {
    changePage(path) {
      this.$router.push({ path })
    },

    handleWidth() {
      document.documentElement.clientWidth <= 768 || window.innerWidth <= 768
        ? (this.isMobile = true)
        : (this.isMobile = false)
    },

    async onSubmit(event) {
      event.preventDefault()
      let continueSubmit = 0
      for (const form in this.registData) {
        if (!this.registerValidationNav(form)) {
          continueSubmit++
          break
        }
      }
      if (continueSubmit === 0) {
        console.log(this.registData)
        let newDate = new Date()
        let nowYear = newDate.getFullYear()
        let nowMonth = newDate.getMonth() + 1
        let nowDate = newDate.getDate()
        let nowHour = newDate.getHours()
        let nowMin = newDate.getMinutes()
        let registTime = `${nowYear}.${nowMonth}.${nowDate} ${nowHour}:${nowMin}`
        // const result = await registerBeforeAuth({
        //   registDate: registTime,
        //   name: this.registData.name.str,
        //   phone: this.registData.phone.str,
        //   email: this.registData.email.str,
        //   address: this.registData.address.str,
        //   party: this.registData.party.str,
        //   participation: this.registData.participation,
        //   category: this.registData.category,
        //   explanation: this.registData.explanation.str,
        //   introduce: this.registData.introduce
        // })
        alert("신청이 완료되었습니다.")
        this.$router.push({ path: "/" })
      }
    },

    registerValidationNav(index) {
      switch (index) {
        case "name":
          return this.checkName()
        case "phone":
          return this.checkPhone()
        case "email":
          return this.checkEmail()
        case "address":
          return this.checkNullText("address")
        case "party":
          return this.checkNullText("party")
        case "participation":
          return this.checkNullRadio("participation")
        case "category":
          return this.checkNullRadio("category")
        case "explanation":
          return this.checkNullText("explanation")
        default:
          return true
      }
    },

    checkNullText(param) {
      if (!this.registData[param].str) {
        param === "address" || param === "party" || param === "phone"
          ? alert(`${this.registData[param].label}를 입력해주세요.`)
          : alert(`${this.registData[param].label}을 입력해주세요.`)
        return false
      }
      return true
    },

    checkNullRadio(param) {
      if (!this.registData[param]) {
        param === "participation"
          ? alert("참석가능날짜를 선택에주세요")
          : alert("문제집 분야를 선택해주세요.")
        return false
      }
      return true
    },

    checkName() {
      if (this.checkNullText("name")) {
        const nameRegex = /^[가-힣]+$/

        let result = nameRegex.test(this.registData.name.str)
        if (!result) {
          alert("이름 형식이 올바르지 않습니다")
          return false
        }
        return true
      }
    },

    checkPhone() {
      if (this.checkNullText("phone")) {
        let numType = this.registData.phone.str.slice(0, 3)
        if (numType !== "010" && numType !== "011" && numType !== "016") {
          alert("번호 형식이 올바르지 않습니다.")
          return false
        }

        if (!this.registData.phone.str.includes("-")) {
          let middleNum = this.registData.phone.str.slice(3, 7)
          let lastNum = this.registData.phone.str.slice(7, 12)
          this.registData.phone.str = `${numType}-${middleNum}-${lastNum}`
        }
        return true
      }
    },

    checkEmail() {
      if (this.checkNullText("email")) {
        const emailRegex = /^[0-9a-zA-Z]([-_\.]?[0-9a-zA-Z])*@[0-9a-zA-Z]([-_\.]?[0-9a-zA-Z])*\.[a-zA-Z]{2,3}$/i

        let result = emailRegex.test(this.registData.email.str)
        if (!result) {
          alert("올바른 이메일 형식으로 입력해주세요.")
          return false
        }
        return true
      }
    }
  }
}
</script>
<style lang="scss">
@import "@/assets/scss/event.scss";
.article-regist {
  text-indent: 10px;

  .guide-ment {
    font-size: 13px;
    margin-left: 3vw;
  }
  .border-radius {
    border-radius: 7px;
  }
  input {
    font-size: 15px;
    &[type="text"],
    &[type="email"],
    &[type="tel"] {
      height: 40px;
      padding-left: 10px;
      border: 1px solid black;
    }
  }

  form {
    .info-title {
      border-bottom: 1px solid #ddd;
      padding-bottom: 10px;
    }

    .regist-info {
      // transition: all 0.5s;
      ul {
        margin: 15px 0 30px;
        li {
          padding: 5px 0;
          label {
            display: inline-block;
            width: 15%;
            text-align: center;
            vertical-align: middle;
          }
          input {
            width: 30%;
            &#address {
              width: 76.5%;
            }
          }
        }
      }
    }
    .regist-add-info {
      .add-info-box {
        padding-top: 30px;
        .info-select {
          display: flex;
          flex-wrap: wrap;
          padding: 10px 0;
          .select-box {
            width: 50%;
            margin: 10px 0;
            label {
              font-size: 15px;
            }
          }
        }
        input[type="radio"] {
          margin-right: 15px;
          vertical-align: middle;
          width: 1.3em;
          height: 1.3em;
        }
        input[type="text"] {
          width: 100%;
          margin: 10px 0;
        }
        textarea {
          resize: none;
          width: 100%;
          min-height: 80px;
          padding: 10px;
          margin: 10px 0;
          font-size: 15px;
        }
      }
    }
    .regist-submit {
      width: 100%;
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
      .btn-radius {
        border-radius: 30px;
        padding: 10px 0;
      }
      .submit-cancle {
        width: 38%;
        background: #ddd;
        color: gray;
        transition: all 0.3s;
        &:hover {
          color: black;
          background: lightgray;
        }
      }
      .submit-agree {
        width: 58%;
        background: #404040;
        color: white;
        transition: all 0.3s;
        &:hover {
          color: black;
          background: #ffe400;
        }
      }
    }
  }
}

@media screen and (max-width: 768px) {
  .article-regist {
    .guide-ment {
      font-size: 11px;
      line-height: unset;
      // text-align: center;
      display: inline-block;
      margin-top: 10px;
    }
    input {
      &[type="text"],
      &[type="email"],
      &[type="tel"] {
        height: 30px;
        font-size: 13px;
      }
    }

    form {
      .info-title {
        font-size: 16px;
      }

      .regist-info {
        ul {
          li {
            label {
              font-size: 13px;
            }
            input {
              width: 40%;
            }
            #email {
              width: 76.5%;
            }
          }
        }
      }
      .regist-add-info {
        .add-info-box {
          .info-select {
            display: unset;
            .select-box {
              width: 100%;
              label {
                font-size: 13px;
              }
            }
          }
          input[type="radio"] {
            width: 1.1em;
            height: 1.1em;
          }
        }
      }
      .regist-submit {
        font-size: 13px;
      }
    }
  }
}
</style>
