<template>
  <div class="regist-list-container">
    <div class="regist-list-article">
      <table>
        <colgroup>
          <col />
          <col />
          <col />
          <col />
          <col />
          <col />
        </colgroup>
        <thead>
          <th>신청시간</th>
          <th>이름</th>
          <th>핸드폰</th>
          <th>이메일</th>
          <th>주소</th>
          <th>소속/회사</th>
        </thead>
        <tbody>
          <tr>
            <td>22.05.24 16:23</td>
            <td>안성환</td>
            <td>010-9698-0600</td>
            <td>gorae@codnut.com</td>
            <td>서울시 광진구 긴고랑로2길 6-6 3층 2030-333</td>
            <td>(주)코드넛</td>
          </tr>
          <tr>
            <td colspan="6" class="add-info-list">
              <ol>
                <li>2022년 7월 16일 1차 밋업</li>
                <li>취업/수험서</li>
                <li>
                  저는 완전 멋진 문제집을 만들거구요, 대치동 학원생들을
                  대상으로한 대단히 멋진 문제집을 만들거에요, 막 그래프가 슝슝
                  날아다니구요, 그래서 200만원에 팔거에요
                </li>
                <li>www.naver.com</li>
              </ol>
            </td>
          </tr>
          <tr>
            <td>22.05.24 16:23</td>
            <td>안성환</td>
            <td>010-9698-0600</td>
            <td>gorae@codnut.com</td>
            <td>서울시 광진구 긴고랑로2길 6-6 3층 2030-333</td>
            <td>(주)코드넛</td>
          </tr>
          <tr>
            <td colspan="6" class="add-info-list">
              <ol>
                <li>2022년 7월 16일 1차 밋업</li>
                <li>취업/수험서</li>
                <li>
                  저는 완전 멋진 문제집을 만들거구요, 대치동 학원생들을
                  대상으로한 대단히 멋진 문제집을 만들거에요, 막 그래프가 슝슝
                  날아다니구요, 그래서 200만원에 팔거에요
                </li>
                <li>www.naver.com</li>
              </ol>
            </td>
          </tr>
        </tbody>
      </table>
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
  }
}
</script>
<style lang="scss">
@import "@/assets/scss/event.scss";
.regist-list-container {
  max-width: 1024px;
  min-height: 100vh;
  margin: 50px auto;
  .regist-list-article {
    table {
      // border: 1px solid black;
      border-collapse: collapse;
      colgroup {
        col {
          &:nth-child(1) {
            width: 15%;
          }
          &:nth-child(2) {
            width: 10%;
          }
          &:nth-child(3) {
            width: 15%;
          }
          &:nth-child(4) {
            width: 15%;
          }
          &:nth-child(5) {
            width: 30%;
          }
        }
      }
      thead {
        th {
          border-bottom: 1px solid black;
          padding: 10px 0;
        }
      }
      tbody {
        tr {
          td {
            padding: 10px 0;
            text-align: center;
            &.add-info-list {
              background: #ddd;
              text-align: left;
              padding: 10px 20px;
              border-bottom: 1px solid black;
              ol {
                li {
                  padding: 7px 0 7px 10px;
                  border-bottom: 1px solid white;
                  &:last-child {
                    border-bottom: none;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
