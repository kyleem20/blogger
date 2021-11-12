<template>
  <div class="search row px-5">
    <div class="col-12">
      <form @submit.prevent="searchBlogs" class="input-group">
        <input @keypress="searchBlogs" v-model="searchText" class="form-control" placeholder="search blogs" type="text"
          name="" id="" />
        <button class="btn btn-outline-primary">search</button>
      </form>
    </div>
  </div>
</template>





<script>
  import { AppState } from "../AppState";
  import { computed, reactive, onMounted } from "vue";
  import { logger } from "../utils/Logger";
  import Pop from "../utils/Pop";
  import { ref } from "@vue/reactivity";
  import { blogsService } from '../services/blogsService';




  export default {
    setup() {
      const searchText = ref("");
      return {
        searchText,
        async searchBlogs() {
          try {
            await blogsService.getAll("?title=" + searchText.value);
          } catch (error) {
            logger.error(error);
            Pop.toast(error.message, "error");
          }
        },
      };
    },
  };
</script>


<style scoped>
</style>