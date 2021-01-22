<template>
  <v-app>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  })
};
</script>
<style lang="sass">
.v-btn:not(.v-btn--round).v-size--default
  height: 36px
  min-width: 64px
  padding: 0 16px
  margin-bottom: 15px
h3
  font-size: 25px!important
h1, h2
  margin-bottom: 10px
h4
  margin-top: 10px
</style>
