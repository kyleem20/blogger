<template>
  <div class="home row">
    <div class="col-12">
      <Search />
    <Threads />
    </div>
  </div>
</template>

<script>
import { onMounted } from '@vue/runtime-core';
import { logger } from "../utils/Logger";
import Pop from "../utils/Pop";
import { blogsService } from "../services/blogsService";
export default {
  name: 'Home',
  setup() {
    onMounted (async () => {
      try {
        await blogsService.getAll();
      } catch (error) {
        logger.error(error);
        Pop.toast(error.message, "error");
      }
    });
    return {};
  },
}
</script>

<style scoped lang="scss">

</style>
