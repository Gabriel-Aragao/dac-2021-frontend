<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      color="primary"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      class="right-padding"
      fixed
      app
    >
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        plain
        to="/login"
      >
        <v-icon>mdi-account</v-icon>
        Login
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
      <v-layout row wrap justify-end class="right-padding">
        <v-btn
          icon
          href="https://github.com/Gabriel-Aragao/"
          target="_blank"
        >
          <v-icon>mdi-github</v-icon>
          Github
        </v-btn>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: true,
      items: [
        {
          icon: 'mdi-library',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-cart',
          title: 'Cart',
          to: '/cart'
        },
        {
          icon: 'mdi-library-shelves',
          title: 'Orders',
          to: '/orders'
        }
      ],
      miniVariant: true,
      right: true,
      title: 'Bookzzz'
    }
  }
}
</script>
<style scoped>
  .right-padding{
    padding-right: 40px;
  }
</style>
