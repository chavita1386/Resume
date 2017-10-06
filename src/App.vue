<template>
  <div id="app"  >
    <app-menu @showMenu="toggleMenu" :class="menu ? 'in': ''"></app-menu>    
    
    <app-aside :cell="data.cell" :email="data.email" :city="data.Locations[0].city" :state="data.Locations[0].state" :country="data.Locations[0].country" :postcode="data.Locations[0].postcode" :educations="data.Education" :skills="data.ProfessionalSkills" :menu="menu" :class="menu ? 'in':''"
    ></app-aside>
    <!-- <app-aside></app-aside> -->
    <app-main :social-networks="data.SocialNetworks" :name="data.name" :last="data.last" :ready="ready" :contents="data.Contents" :menu="menu"></app-main>  
  </div>
</template>

<script>
import moment from 'moment';
import axios from 'axios';
// import appHeader from './components/app-header/appHeader.vue';
import appSocial from './components/app-social/appSocial.vue';
// import appContent from './components/app-content/appContent.vue';
import appAside from './components/app-aside/appAside.vue';
import appMenu from './components/app-menu/appMenu.vue';
import appMain from './components/app-main/appMain.vue';

export default {
  name: 'app',
  components: {  appSocial, appAside, appMenu, appMain },
  data() {
    return {
      msg: 'Resume',
      menu: false,
      ready: false,
      scrolled: false,
      data: {
        Locations: [{}]
      }
    }
  },
  mounted() {
    //console.warn('Created: ' + moment().format('HH:mm:ss'));    
    axios.get('http://chetur.com/api/user/')
      .then((response) => {        
        this.data = response.data.users[0];
        this.ready = true;        
      })
      .catch((response) => {
        //console.log(reponse);
      });
  },
  created () {    
      
  },
  methods: {
    toggleMenu() {
      // console.log('App toggleMenu');
      // console.log(this.menu);
      this.menu = !this.menu;
      // console.log(this.menu);
    },
    closeMenu() {
      // console.log('App closeMenu');
      this.menu = false;
    }    
  }
}
</script>

<style lang="scss" src='./scss/app.scss'>

</style>
