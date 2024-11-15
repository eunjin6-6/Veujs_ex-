<script setup>
  import { ref } from 'vue';

  //초기값 설정
  const awesome = ref(true)
  const type = ref('D')
  const page = ref(true)

  //함수로 
  //computed 함수는 값을 계산하고 반환반 할 수 있음, 상태 변경 불가
  const myfunc = ()=> {
    awesome.value = !awesome.value
  }

</script>


<template>
  <button @click="page = !page">페이지 전환</button>
 
  <!-- <div class="content">
    <h1>조건부 렌더링</h1>

    <div v-if="awesome">Vue는 정말 멋지죠!</div>
    <div v-else>아닌가요? 😢</div>
    
    <button @click="awesome = !awesome">toggle button</button>
    <button @click="myfunc">func button</button>

    <hr>

    <div v-if="type === 'A'">
      A
    </div>
    <div v-else-if="type === 'B'">
      B
    </div>
    <div v-else-if="type === 'C'">
      C
    </div>
    <div v-else>
      A/B/C 아님
    </div>
  </div> -->

  <template v-if="page">
    <h1>page 1 </h1>
  </template> 
  <template v-if="page == false">
    <h1>page 2 </h1>
  </template> 
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
