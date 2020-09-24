<template>
  <div>
    <svg
      v-for="(color, index) in colors"
      :key="index"
      xmlns="http://www.w3.org/2000/svg"
      width="110"
    >
      <path :fill="color" d="M1,44h107l-87,63 33-102 33,102z" />
    </svg>
  </div>
</template>

<script>
import { computed } from "@vue/composition-api";
// import { computed } from "@vue/composition-api";
export default {
  props: {
    rating: {
      type: Number,
      default: 0
    }
  },
  // computed: {
  //   colors() {
  //     const colors = ["grey", "grey", "grey", "grey", "grey"];
  //     return colors.map((c, i) => {
  //       return i < this.rating ? "yellow" : "grey";
  //     });
  //   }
  // }
  setup(props, context) {
    // ['Yellow', 'yellow', 'grey', 'grey', 'grey']
    const colors = computed(() => {
      console.log("attrs : ", context.attrs);
      const colors = [];
      let i = 0;
      while (i++ < 5) {
        colors.push(i < props.rating ? "yellow" : "grey");
      }
      return colors.map((c, i) => {
        return i < props.rating ? "yellow" : "grey";
      });
    });
    return { colors };
  }
};
</script>

<style></style>
