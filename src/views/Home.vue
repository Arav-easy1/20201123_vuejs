<template>
  <div>
    <h1>Welcome to {{ title }}!</h1>
    <input type="text" v-model="input1" />
    <button type="button" @click="getData()">Get</button>
    <button type="button" @click="setData()">Set</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "Arav",
      title2: "easy1",
      input1: "one two three",
    };
  },
  methods: {
    getData() {
      alert(this.input1);
    },
    setData() {
      this.input1 = "12345";
    },
  },
};
</script>
