<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <p> Check my Projects!</p>
    
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
    

      
        <v-list 
        nav 
        dense>
          <v-list-item
            class="ver-nav-bar"
            v-for="item in items"
            :key="item.icon"
            router

          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
          </v-list-item>
        </v-list>
     
<!--Start top App bar where you can add -->
    <v-app-bar
      fixed
      app
    >

    <!-- button that activates side bar -->
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
    <!-- my name displayed on nav bar -->
      <nuxt-link to="/" class="brand" v-text="title"></nuxt-link>
      <v-spacer />
    </v-app-bar>


    

<!-- web page content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    

    <!-- footer     -->
    <v-footer
      :fixed="fixed"
    
    >
    <v-spacer></v-spacer>
      <span >Alejandro Torrico   &copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        },
        {
          icon: 'mdi-webhook',
          title: 'Hershey',
          to: '/hershey-mso'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Alejandro Torrico',
      to: '/'
    }
  }
}
</script>
<style scoped>
.brand {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  font-size: 1.5em;
  color: #39b982;
  text-decoration: none;
}
.ver-nav-bar {
  top: 60px
}
</style>
