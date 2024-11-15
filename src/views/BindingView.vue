<script setup>
  import { ref, reactive, computed } from 'vue';

  //초기값 설정
  const isActive = ref(true)
  const hasError = ref(false)
  //true, false 인지에 따라 클래스명 다르게 적용됨


  const classObject = reactive({
    active: true,
    error: false
  })

  
  //함수사용
  const myfunc = computed(() => {
    return {
      active: isActive.value && !hasError.value ,
      error: hasError.value
    }
  })

</script>

<template>
  <div class="content">
    <h1>클래스와 바인딩</h1>
    <div class="static" :class="{ 'active': isActive, 'error': hasError }">content 1</div>
    <!-- zmffotmaud static, active 출력 -->

    <div class="static" :class="classObject">content 2</div>

    <div class="static" :class="myfunc">content 3</div>
  </div>
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
