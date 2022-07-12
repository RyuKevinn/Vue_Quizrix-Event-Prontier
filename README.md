# Vue_Quizrix-Event-Prontier

<h3>파일 구조 </h3>

![스크린샷 2022-07-12 오후 2 58 49](https://user-images.githubusercontent.com/96170774/178419299-e869fad9-daf4-4ea0-87fe-b8265395dffe.png)

![스크린샷 2022-07-12 오후 2 20 25](https://user-images.githubusercontent.com/96170774/178417920-1107ef69-a7a9-4dd9-aeb3-89c93dd2920f.png)

![스크린샷 2022-07-12 오후 2 55 51](https://user-images.githubusercontent.com/96170774/178418866-e743f466-2bf8-49a4-9da0-108de739a265.png)


<h3>pages</h3> 

  - event 
      - :pontier
<hr>
<h3>components</h3>
  - index.vue
  - ProntierRegist.vue
  - ProntierList.vue
<hr>
<h3>layouts</h3>
  - event-layout.vue
<hr>
<h3>Url 구조</h3> 
<ul>
  <li>https://********.com/event/prontier</li>
  <li>https://********.com/event/regist</li>
  <li>https://********.com/event/regist-list</li>
</ul>

<hr>

<h2> ProntierRegist.vue </h2>

![스크린샷 2022-07-12 오후 2 22 41](https://user-images.githubusercontent.com/96170774/178419872-55cc3044-0437-4147-9ffa-4b47a01e14e7.png)

![스크린샷 2022-07-12 오후 2 23 07](https://user-images.githubusercontent.com/96170774/178419938-53f5562a-2f0d-4cf0-a86e-312bdff19c64.png)

  v-for 를 사용하여 data 내에 있는 자료들 구현


![스크린샷 2022-07-12 오후 2 23 36](https://user-images.githubusercontent.com/96170774/178420047-512dc118-d335-4d40-a698-ed1f4cc158e9.png)

![스크린샷 2022-07-12 오후 2 24 51](https://user-images.githubusercontent.com/96170774/178420100-478eac88-97b4-40e0-86ad-2b412563a6f4.png)

![스크린샷 2022-07-12 오후 2 25 09](https://user-images.githubusercontent.com/96170774/178420274-585a0941-6439-4ac3-8c0a-08caa1fbd002.png)

![스크린샷 2022-07-12 오후 2 25 33](https://user-images.githubusercontent.com/96170774/178420333-69491e18-4fbe-4cc4-8fd8-06335376996a.png)

![스크린샷 2022-07-12 오후 2 25 55](https://user-images.githubusercontent.com/96170774/178420572-2102b7a0-d4e6-40f5-9f96-4aef0d931d0c.png)

![스크린샷 2022-07-12 오후 2 26 22](https://user-images.githubusercontent.com/96170774/178420593-4f57afb9-716f-4221-8e3b-0be0601fef6e.png)

<p>data 내부에 있는 자료들을 v-model 로 연결하여 submit 이벤트 발생 시 유효성 검사 실행</p>
<p>유효성 검사 Nav switch-case 문을 통해서 param 값에 따라 해당 함수에 맞게 연결</p>
<p>1차 null 값 판단 후 정규식 혹은 함수를 사용한 2차 유효성 검사</p>
<p>검사 후 api에 데이터 보내기</p>

![스크린샷 2022-07-12 오후 2 27 12](https://user-images.githubusercontent.com/96170774/178420774-46c43163-7d00-4125-b4d2-3a23b87093a3.png)


<h2> ProntierList.vue </h2>
<p>Regist 완료된 정보들을 api 호출로 데이터 리스트업</p>

![스크린샷 2022-07-12 오후 2 26 46](https://user-images.githubusercontent.com/96170774/178421217-29ae3133-ce29-40f3-a99e-c78830de444b.png)

