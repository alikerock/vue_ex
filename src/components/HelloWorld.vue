<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  },
  msg2: {
    type: String,
    required: true
  },
  
});
const rawHtml= '<a href="">Link</a>';
const pid = 10;
const isButtonDisabled = true;
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
}
const number = 20;
const ok = false;
const message= "안녕하세요";
const id = 30;
const sayHello = (msg)=>{
 alert(msg);
}
const seen = true;
const items = [
  {id:0, title:'제목1'},
  {id:1, title:'제목2'},
  {id:2, title:'제목3'}
]
let url = 'http://www.abc.com/'
let attributeName = 'href';
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}{{ msg2 }}</h1>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
    <hr>
    <p>텍스트 보간법 사용: {{ rawHtml }}</p>
    <p>v-html 디렉티브 사용: <span v-html="rawHtml"></span></p>
  </div>
  <div v-bind:id="pid">
    <p>프로젝트 id: {{ pid }}</p>
    <button :disabled="isButtonDisabled">버튼</button>
    <button :disabled="!isButtonDisabled">버튼</button>
    
    <div v-bind="objectOfAttrs"></div>
    <div>
      <p>{{ number + 1 }}</p>
      <p>{{ ok ? '예' : '아니오' }}</p>
      <p>{{ message.split('').reverse().join('') }}</p>
      <p :id="`list-${id}`">{{ id }}</p>
    </div>
    <time :title="sayHello('hello')"></time>
    <p v-if="seen">이제 이것을 볼 수 있습니다.</p>
  </div>
  <ul v-for="item in items" :key="item.id">
    <li>{{ item.title }}
    </li>
  </ul>
  <div>
    <a v-bind:href="url"> abc </a>
    <a :href="url"> abc </a>
    <a href="url"> abc </a>    
  </div>
  <div>
    <button type="button" @click="sayHello('안녕')">경고</button>
  </div>
  <div>
    <a :[attributeName]="url"> 동적인 인자 </a>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
