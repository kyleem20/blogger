<template>
  <header>
    <Navbar />
  </header>
  <main class="container-fluid">
    <router-view />
  </main>
  <footer class="footer">
    <div class="bg-dark text-light text-center p-4">
      Made with 🎾
    </div>
  </footer>
</template>

<script>
import { computed } from 'vue'
import { AppState } from './AppState'
export default {
  name: 'App',
  setup() {
    return {
      appState: computed(() => AppState)
    }
  }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";
// #footer {
//   position: fixed;
//     height: 50px;
//     background-color: red;
//     bottom: 0px;
//     left: 0px;
//     right: 0px;
//     margin-bottom: 0px;
// }
</style>
