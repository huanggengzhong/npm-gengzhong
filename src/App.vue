<template>
  <div>
    <h3>gengzhong-component</h3>
    <span ref="countup"></span>
  </div>
</template>

<script>
// 使用方式:
// <vue-count-up :end="2500" :duration="2.5"></vue-count-up>
import { CountUp } from "countup.js";
export default {
  name: "Countupdemo",
  props: {
    end: {
      type: Number,
      default: 2020
    },
    decimal: {
      type: Number,
      default: 0
    },
    duration: {
      type: Number,
      default: 2.5
    },
    options: {
      type: Object
    }
  },
  data() {
    return {
      numAnim: null
    };
  },
  mounted() {
    this.initCountUp();
  },
  methods: {
    initCountUp() {
      this.numAnim = new CountUp(this.$refs.countup, 
                           this.end,
                           this.decimal,
                           this.duration,
                           this.options
      );
      this.numAnim.start();
    }
  }
};
</script>

<style></style>
