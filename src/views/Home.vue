<template>
  <div
    class="home"
    style="
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
      padding-left: 35%;
    "
  >
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1>Home页</h1>
    <div style="margin-bottom: 2em">
      <span>变量A：</span><span>{{ A }}</span>
      <button @click="() => this.A++" style="margin-left: 2em">加1</button>
    </div>
    <div style="margin-bottom: 2em">
      <span>变量B：</span><span>{{ B }}</span>
      <button @click="() => this.B++" style="margin-left: 2em">加1</button>
    </div>
    <div style="margin-bottom: 2em">
      <span><i style="color:red;">Computed</i> 监控<i style="color:red;">A和B两者</i>的变化：</span><span>{{ AaddB }}</span>
    </div>
    <div style="margin-bottom: 2em">
      <span><i style="color:red;">Watch</i> 监控<i style="color:red;">A</i>的变化 => </span
      ><span>变化前的A：{{ oldA }} 变化后的A：{{ newA }}</span>
    </div>
    <div style="margin-bottom: 2em">
      <span><i style="color:red;">Watch</i> 监控<i style="color:red;">B</i>的变化 => </span
      ><span>变化前的B：{{ oldB }} 变化后的B：{{ newB }}</span>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "Home",
  components: {
    // HelloWorld
  },
  data() {
    return {
      A: 1,
      B: 100,
      oldA: 1,
      newA: undefined,
      oldB: 100,
      newB: undefined,
    };
  },
  watch: {
    A: {
      handler(n, o) {
        this.oldA = o;
        this.newA = n;
      },
    },
    B: {
      handler(n, o) {
        this.oldB = o;
        this.newB = n;
      },
    },
  },
  computed: {
    AaddB() {
      return this.A + this.B;
    },
  },
};
</script>
