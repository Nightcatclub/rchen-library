<script>
import JSONLab from './components/JSONLab.vue'
import BHeader from './components/BHeader.vue'
import LibraryRegistrationForm from './components/LibraryRegistrationForm.vue'
import CountBookAPI from './views/CountBookAPI.vue';

export default {
  name:'APP',
  components:{
    BHeader,
    CountBookAPI
  },
  computed: {
    ShowHeader() {
      return this.$route.name !== 'CountBookAPI';
    }
  }
};
</script>

<template>
  <div class="main-container">
    <header v-if="ShowHeader">
    <BHeader />
  </header>

  <main class="main-box">
    <router-view></router-view>
    <!-- <LibraryRegistrationForm /> -->
    <!-- <JSONLab /> -->
  </main>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
.container {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  max-width: 80vw;
  margin: 0 auto;
  padding: 20px;
  background-color: #be3a81;
  border-radius: 10px;
}
</style>
