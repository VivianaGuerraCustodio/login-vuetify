<template>
  <v-app>
    <v-main>
      <v-container>
        <v-navigation-drawer
          v-model="drawer"
          :mini-variant.sync="mini"
          permanent
        >
           <v-list-item class="px-2">
            <v-list-item-avatar>
              <v-img
                src="https://randomuser.me/api/portraits/lego/1.jpg"
              ></v-img>
            </v-list-item-avatar>

            <v-list-item-title></v-list-item-title>

            <v-btn icon @click.stop="mini = !mini">
              <v-icon>mdi-chevron-left</v-icon>
            </v-btn>
          </v-list-item>

          <v-divider></v-divider>

          <v-list dense>
            <v-list-item v-for="item in items" :key="item.title" link>
              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-navigation-drawer>
      </v-container>
    </v-main>
  </v-app>
</template>
<script>
export default {
  data() {
    return {
      drawer: true,
      items: [
        { title: "Inicio", icon: "mdi-home-city" },
        { title: "Mi cuenta", icon: "mdi-account" },
        { title: "Compañeros", icon: "mdi-account-group-outline" }
      ],
      mini: true
    };
  },
  mounted() {
    alert("El dashboard está vacío");
  }
};
</script>
<style lang="sass" scoped>
.container
  width: 100%
  padding: 0
  margin: 0
  height: 100vh
</style>