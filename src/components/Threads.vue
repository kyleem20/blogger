<template>
  <div class="threads row">
    <div v-for="b in blogs" :key="b.id" class="col-md-11">
      <Blog :blog="b" />
    </div>
  </div>
</template>


<script>
import { AppState } from "../AppState";
import { computed, reactive, onMounted } from "vue";
export default {
  setup() {
    return {
      blogs: computed(() => AppState.blogs),
    };
  },
};
</script>


<style scoped>
</style>