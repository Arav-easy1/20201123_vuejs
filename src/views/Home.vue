<template>
  <div>
    <h1>Welcome to {{ title }}!</h1>
    <input type="text" v-model="input1" />
    <button type="button" @click="getData()">Get</button>
    <button type="button" @click="setData()">Set</button>

    <select class="form-control" v-model="region" @change="changeRegion()">
      <option :key="i" :value="d.v" v-for="(d, i) in options">{{ d.t }}</option>
    </select>

    <!-- v-if와 v-show의 차이점:
        - 둘다 해당 조건이 false일때는 안보이고 true일때는 보이는 것은 같지만,
        v-if는 false일 경우 아예 rendering조차 되지 않고,
        v-show는 invisible인 형태처럼 rendering은 되어있지만 화면에 보여지지는 않는다.
        따라서, 화면에서 자주 보였다 안보였다 하는 기능을 처리할 때는 v-show를 사용해야 resource를 덜 잡아먹는다. -->
    <table class="table table-bordered" v-if="tableShow">
      <tr :key="i" v-for="(d, i) in options">
        <td>{{ d.v }}</td>
        <td>{{ d.t }}</td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "Arav",
      title2: "easy1",
      input1: "one two three",
      options: [
        { v: "S", t: "Seoul" },
        { v: "J", t: "Jeju" },
        { v: "B", t: "Busan" },
      ],
      region: "J",
      tableShow: false,
    };
  },
  // 특정 데이터가 변경되는 시점에 특정 작업을 실행 할 수 있도록 해준다. (watch)
  watch: {
    input1() {
      console.log(this.input1);
    },
  },
  methods: {
    getData() {
      alert(this.input1);
    },
    setData() {
      this.input1 = "12345";
    },
    changeRegion() {
      alert(this.region);
    },
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  created() {
    console.log("created");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  mounted() {
    console.log("mounted");
  },
  beforeUpdate() {
    console.log("beforeUpdate");
  },
  updated() {
    console.log("updated");
  },
  beforeDestroy() {
    console.log("beforeDestroy");
  },
  destroyed() {
    console.log("destroyed");
  },
};
</script>
