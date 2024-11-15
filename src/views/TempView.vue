<script setup>
const rawHTML = '<a href="">Link</a>';
const pid = 10;
const isButtonDisabled = true;

const objectAttr = {
  id: 'container',
  class: 'wrapper'
}
const number = 30;
const ok = false;
const message = "안녕";

const sayHello = (msg)=>{
  //alert(msg);
  console.log(msg)
  return '인사';
}
const items = [
  {id:0, title: '제목1'},
  {id:1, title: '제목2'},
  {id:2, title: '제목3'}
]

const seen = true;

const url = 'http://www.abc.com';

const openAlert = (text)=>{
  alert(text);
}

let attrName = 'href';

const sendform = ()=>{

}
</script>

<template>
  <div class="temp">
    <h1>기초 문법 페이지</h1>
    <div class="greetings" v-bind="objectAttr">
      <p>텍스트 출력 보간법: {{ rawHTML }}</p>
      <p>v-html(속성) 디렉티브 사용: <span v-html="rawHTML"></span></p>
    </div>
  <div v-bind:id="pid">프로젝트 id: {{ pid }}</div>
  <button>버튼1</button>
  <button disabled>버튼2</button>
  <button :disabled="!isButtonDisabled">버튼2</button>
  <button :disabled="isButtonDisabled">버튼2</button>
  <hr>
  <div>
    <p>{{ number + 1 }}</p>
    <p>{{ ok ? '예' : '아니오' }}</p>
    <p>{{ message.split('').reverse().join('') }}</p>
    <p v-bind:id="pid">id: {{ pid }}</p>
    <p :id="pid">id: {{ pid }}</p>
    <!-- 표현식만 가능(값 출력, 연산) -->
    <!-- <p>{{ var a = 1; }}</p> 선언식(statement) 불가 -->
    <!-- <p>{{ if(ok){'에'}else{'아니오'} }} if문 불가 -> 삼항표현식 사용</p> -->

    <span :title="sayHello('안녕')"></span>
    {{ sayHello('안녕2') }}

    {{  seen ? '<p>볼수있다</p>' : '볼수없다' }}
    <p v-if="!seen">내용을 볼 수 있어요</p>
    
    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.title }}
      </li>
    </ul>

    <a v-bind:href="url">abc</a>
    <a :href="url">abc malll</a>
    <a href="url">abc</a>

    <button v-on:click="openAlert('경고')">경고 띄우기</button>
    <button @click="openAlert('경고')">경고 띄우기</button>
    <hr>
    
    동적 바인딩
    <a v-bind:href="url">abc</a>
    <a :[attrName]="url">abc</a>
    <hr>
    <form action="" @submit.prevent="sendform">
      <input type="text">
      <button type="submit">전송</button>
    </form>
  </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .temp {
    min-height: 100vh;

  }
}
</style>
