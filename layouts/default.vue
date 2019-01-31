<template>
  <v-app>
    <v-navigation-drawer :mini-variant="miniVariant" :clipped="clipped" v-model="drawer" fixed app>

 <v-list>
        <v-list-tile v-for="(item, i) in items" :to="item.to" :key="i" router exact>
          <v-list-tile-action>
            <v-icon v-html="item.icon"/>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"/>
          </v-list-tile-content>
        </v-list-tile>

<v-tabs
      v-model="active"
      color="cyan"
      dark
      slider-color="red"
    >
      <v-tab
        v-for="n in 3"
        :key="n"
        ripple
      >
        Item {{ n }}

      </v-tab>
      <v-tab-item
        v-for="n in 3"
        :key="n"
      >
        <v-card flat>
          <v-card-text>{{ text }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs>

  
        
      </v-list>

  </v-navigation-drawer>
    <v-toolbar :clipped-left="clipped" fixed app>
      <v-toolbar-side-icon @click="drawer = !drawer"/>
   <v-toolbar-title v-text="title"/>   
   <v-text-field
        append-icon="mic"
        class="mx-3"
        flat
        label="Search"
        prepend-inner-icon="search"
        solo-inverted
      ></v-text-field>

    </v-toolbar>
  <v-content>
    <v-container fluid>
      <router-view></router-view>
    </v-container>
  </v-content>
  
    <v-footer :fixed="fixed" app>
      <span>&copy; 2019</span>
    </v-footer>
</v-app>
</template>

<script>
import Sidebar from '@/components/Sidebar'
import Header from '@/components/Header'
import Footer from '@/components/Footer'

export default {
  components: {
    Sidebar,
    Header,
    Footer
  },
    data() {
    return {
      active:false,
      clipped: true,
      drawer: true,
      fixed: false,
      items: [
        { icon: "apps", title: "INICIO", to: "/" },
        { icon: "language", title: "LOCAL", to: "/" },
        { icon: "language", title: "NACIONAL", to: "/" },
        { icon: "language", title: "INTERNACIONAL", to: "/" },
        
        { icon: "language", title: "EDITORIALES", to: "/" },
        { icon: "language", title: "SEGURIDAD", to: "/" },
        { icon: "language", title: "TECNOLOGIA", to: "/" },
        { icon: "language", title: "SOCIALES", to: "/" },
        { icon: "language", title: "DEPORTES", to: "/" },
        { icon: "language", title: "FINANZAS", to: "/" },

        { icon: "group_work", title: "info", to: "/about" }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "DGONOTICIAS"
    };
  }
}
</script>
