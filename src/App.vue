<template>
  <v-app>
    <HeaderApp></HeaderApp>
    <SidebarApp></SidebarApp>
    <!--<<ContentAppDos></ContentAppDos>-->
    <ContentApp></ContentApp>
  </v-app>
</template>

<script>
import HeaderApp from './components/HeaderApp';
import SidebarApp from './components/SidebarApp';
import ContentApp from './components/ContentApp';
//import ContentAppDos from './components/ContentAppDos';

export default {
  name: 'App',

  components: {
    HeaderApp,
    SidebarApp,
    ContentApp,
    //ContentAppDos,
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
@import './assets/css/style.css';
</style>
