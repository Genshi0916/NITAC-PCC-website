<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      v-if="$vuetify.breakpoint.mobile"
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
      fixed
      app
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" v-if="$vuetify.breakpoint.mobile" />
      <v-toolbar-title v-text="title" />
      <Header v-if="!$vuetify.breakpoint.mobile"></Header>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer
      :absolute="!fixed"
      app
    >
      <div class="flex-grow-1"></div>
      <v-icon>mdi-gmail</v-icon>
      genshi0916@gmail.com
    </v-footer>
  </v-app>
</template>

<script>
import Header from '../components/header'
export default {
  comments:{
    Header,
  },
  data () {
    return {
      clipped: false,
      drawer: null,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Activities',
          to: '/activities'
        },
        {
          icon: 'mdi-card-account-mail-outline',
          title: 'Contact',
          to: '/contact'
        },
        {
          icon: 'mdi-twitter',
          title: 'about',
          to: '/about'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '旭川高専パソコン部'
    }
  }
}
</script>
