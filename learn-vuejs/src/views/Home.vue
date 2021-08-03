<template>
  <div>
    <h1>Welcome to Home !</h1>
    <input type="text" v-model="input" />
    <button type="button" @click="getData">Get</button>
    <button type="button" @click="setData">Set</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      input: 'abc',
    };
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
  beforeUpdate() {
    console.log('beforeUpdate');
  },
  updated() {
    console.log('updated');
  },
};
</script>
