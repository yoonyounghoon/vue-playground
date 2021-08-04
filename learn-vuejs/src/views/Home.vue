<template>
  <div>
    <h1>Welcome to Home !</h1>
    <input type="text" v-model="input" />
    <button type="button" @click="getData">Get</button>
    <button type="button" @click="setData">Set</button>
    <img v-bind:src="imageSource" alt="random-image" />
    <a :href="naverUrl">Naver</a>
    <hr />
    <h2 :class="{ red: input === 'apple', done: input === 'apple' }">
      동적으로 클래스 주기
    </h2>
    <hr />
    <input type="text" v-model="inputAge" />
    <h2>당신의 나이는 {{ inputAge }}세입니다.</h2>
    <h3 v-if="inputAge > 19">당신은 성인입니다.</h3>
    <h3 v-else-if="inputAge > 13 && inputAge <= 19">당신은 청소년입니다.</h3>
    <div>
      <h2 v-for="(animal, index) in animals" :key="index">{{ animal }}</h2>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      input: '',
      inputAge: '',
      imageSource: 'https://placeimg.com/100/100/any',
      naverUrl: 'https://www.naver.com',
      animals: ['monkey', 'dog', 'cat'],
    };
  },
  watch: {
    input() {
      console.log(this.input);
    },
  },
  methods: {
    getData() {
      console.log(this.input);
    },
    setData() {
      this.input = '12345';
    },
  },
  beforeCreate() {
    console.log('beforeCreate');
  },
  created() {
    console.log('created');
  },
  beforeMount() {
    console.log('beforeMount');
  },
  mounted() {
    console.log('mounted');
  },
  // beforeUpdate() {
  //   console.log('beforeUpdate');
  // },
  // updated() {
  //   console.log('updated');
  // },
};
</script>
<style>
.red {
  color: red;
}

.done {
  text-decoration: line-through;
}
</style>
