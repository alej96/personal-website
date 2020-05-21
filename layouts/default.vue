<template>
  <v-app dark>
    <v-navigation-drawer
        expand-on-hover
        permanent
        fixed
        app
    >
      <v-list>
         <v-list-item class="px-2">
        <v-list-item-avatar>
          <v-img src="https://media-exp1.licdn.com/dms/image/C4E03AQHz7BIKr8pe_A/profile-displayphoto-shrink_200_200/0?e=1594252800&v=beta&t=iYx88s-NDlZPDci8XuA86hpyXSErj9lTTKJTxeiIegg"></v-img>
        </v-list-item-avatar>

        <v-list-item-title>Check out my projects!</v-list-item-title>

      </v-list-item>
      </v-list>
      <v-divider></v-divider>
    
      <v-list 
        nav
        dense
      >
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          link
          
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
     
<!--Start top App bar where you can add -->
    <v-app-bar
      fixed
      app
    >

    <!-- button that activates side bar -->
      <!-- <v-app-bar-nav-icon @click.stop="drawer = !drawer" /> -->
    <!-- my name displayed on nav bar -->
      <nuxt-link to="/" class="brand" v-text="title"></nuxt-link>
      <v-spacer></v-spacer>
      <nav>
        <!-- <nuxt-link to="/about-me" class="hor-nav-bar">About Me</nuxt-link>&nbsp;|&nbsp;
        <nuxt-link to="/portfolio" class="hor-nav-bar">Portfolio</nuxt-link> -->
         <nuxt-link 
          class="top-nav-bar"
          v-for="(topNavItem, t) in topNavItems"
          :key="t"
          :to="topNavItem.to"
          link
          >
          | &nbsp; {{ topNavItem.name }} &nbsp; |
          
         </nuxt-link>
    </nav>
      <!-- <v-spacer /> -->
    </v-app-bar>


    

<!-- web page content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    

    <!-- footer     -->
    <v-footer>
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
      drawer: true,
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
          icon: 'mdi-candycane',
          title: 'Hershey',
          to: '/hershey-mso'
        },
        {
          icon: 'mdi-cash-multiple',
          title: 'Business Inteligence',
          to: '/storage-bi'
        }
      ],
      topNavItems: [
        {
          name: 'Portfolio',
          to:'/portolio'
        },
        {
           name: 'About Me',
           to: '/about-me'
        },
        {
          name: 'Connect',
          to:'/connect'
        }

      ],
      mini: true,
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
.top-nav-bar {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  font-size: 1.2em;
  color: #39b982;
  text-decoration: none;
}
</style>
