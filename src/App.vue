<template>
  <!-- v-if : 해당 조건이 참일 때만 해당 태그 영역을 보여줌 -->
  <div class="black-bg" v-if="modal_status == true">
    <div class="white-bg">
      <div class="close-area">
        <button @click="modal_status = false" class="modal-close">&times;</button>
      </div>
    <h4>상세페이지</h4>
    <p>상세페이지 내용</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>

  <div>
    <img src="./assets/room0.jpg" class="room-img"/>
    <h4 @click="modal_status = true">{{ products[0] }}</h4>
    <p>{{ price1 }} 만원</p>
    <!-- v-on: 대신 @로 대체할 수 있음. -->
    <button @click="increase(0)">허위매물신고</button>
    <span> 신고수 : {{ 신고수[0] }}
    </span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img"/>
    <h4>{{ products[1] }}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="increase(1)">허위매물신고</button>
    <span> 신고수 : {{ 신고수[1] }}
    </span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img"/>
    <h4>{{ products[2] }}</h4>
    <p>{{ price3 }} 만원</p>
    <button @click="increase(2)">허위매물신고</button>
    <span> 신고수 : {{ 신고수[2] }}
    </span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      modal_status: false,
      신고수 : [0, 0, 0],
      price1 : 67,
      price2 : 70,
      price3 : 80,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods: {
    increase(i) {
      this.신고수[i] += 1;
    }
  },
  components: {
  }
}
</script>

<style>
.close-area {
  text-align: right;
}

.modal-close {
    display: inline-block;
    font-weight: 400;
    color: #212529;
    background-color: transparent;
    border: 1px solid transparent;
    font-size: 1rem;
    line-height: 1.5;
    border-radius: .25rem;
    cursor: pointer;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
