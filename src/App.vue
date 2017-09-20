<template>
  <div id="app">
    <app-menu @showMenu="toggleMenu" :class="menu ? 'in': ''"></app-menu>    

    <app-aside :cell="data.cell" :email="data.email" :city="data.Locations[0].city" :state="data.Locations[0].state" :country="data.Locations[0].country" :postcode="data.Locations[0].postcode" :educations="data.Educations" :skills="data.ProfessionalSkills" :class="menu ? 'in':''"
    ></app-aside>
    
    <app-social :social-list="data.SocialNetworks" :class="menu ? 'in':''"></app-social>
    <app-header :name="data.name" :last="data.last" :class="menu ? 'in':''"></app-header>

    <main class="main" :class="menu ? 'in':''">
      <app-content v-for="item in data.Contents" :key="item.idContent" :text="item.contentText" :title="item.title"></app-content>
    </main>
    
    
  </div>
</template>

<script>
import moment from 'moment';
import axios from 'axios';
import appHeader from './components/app-header/appHeader.vue';
import appSocial from './components/app-social/appSocial.vue';
import appContent from './components/app-content/appContent.vue';
import appAside from './components/app-aside/appAside.vue';
import appMenu from './components/app-menu/appMenu.vue';

export default {
  name: 'app',
  components: { appHeader, appSocial, appContent, appAside, appMenu },
  data() {
    return {
      msg: 'Resume',
      menu: false,
      data: ''
    }
  },
  mounted() {
    //console.warn('Created: ' + moment().format('HH:mm:ss'));
    axios.get('http://bossinovations.com.stem.arvixe.com/api/Usuario/2')
      .then((response) => {
        //console.log(response.data);
        this.data = response.data;
        //console.warn('data:' + moment().format('HH:mm:ss'));
      })
      .catch((response) => {
        //console.log(reponse);
      });
  },
  methods: {
    toggleMenu() {
      console.log('App toggleMenu');
      console.log(this.menu);
      this.menu = !this.menu;
      console.log(this.menu);
    },
    closeMenu() {
      console.log('App closeMenu');
      this.menu = false;
    }
  }
}
</script>

<style lang="scss" src='./scss/app.scss'>

</style>
