<template>
  <v-app>
    <v-main>
      <Header/>
      <Questionnaire/>
    </v-main>
  </v-app>
</template>

<script>
import Header from './components/Header';
import Questionnaire from './components/Questionnaire';

export default {
  name: 'App',

  components: {
    Header,
    Questionnaire
  },
  created() {
    this.$vuetify.rtl = true
  },

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
 @import '@/styles/main';
</style>
