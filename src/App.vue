<template>
  <div>
    <div class="loading" v-if="loading">
      <svg class="lds-blocks" width="100px" height="100px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 100 100" preserveAspectRatio="xMidYMid" style="background: none;">
        <rect x="19" y="19" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0s" calcMode="discrete"></animate>
        </rect>
        <rect x="40" y="19" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.125s" calcMode="discrete"></animate>
        </rect>
        <rect x="61" y="19" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.25s" calcMode="discrete"></animate>
        </rect>
        <rect x="19" y="40" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.875s" calcMode="discrete"></animate>
        </rect>
        <rect x="61" y="40" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.375s" calcMode="discrete"></animate>
        </rect>
        <rect x="19" y="61" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.75s" calcMode="discrete"></animate>
        </rect>
        <rect x="40" y="61" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.625s" calcMode="discrete"></animate>
        </rect>
        <rect x="61" y="61" width="20" height="20" fill="#8cd0e5">
          <animate attributeName="fill" values="#376888;#8cd0e5;#8cd0e5" keyTimes="0;0.125;1" dur="1s" repeatCount="indefinite" begin="0.5s" calcMode="discrete"></animate>
        </rect>
      </svg>
    </div>
    <div v-if="!loading" class="to-m" @click="toggleMenu = !toggleMenu" :class="toggleMenu ? 'menu in': 'menu hide'">
      <!-- <label>{{ toggleMenu ? 'Close': 'Contact'}}</label> -->
      <!-- <span class="icon-address-book"></span> -->
    </div>
    <!--      ASIDE     -->
    <aside class="item m-35 l-25" :class="toggleMenu ? 'aside in':'aside hide'">
      <div class="content">
        <div class="profile">
          <figure class="photo">
            <img src="./assets/profile.png" class="photo__img" :alt="name">
          </figure>
        </div>
        
        <asideTitle title="Contact"></asideTitle>   


        <contact class="padding" :email="email" :cell="cell" :location="location"></contact>

        <social :socialItem="socialNetwork"></social>     
        <!-- <social class="padding" :socialItem="socialNetwork"></social> -->

        <asideTitle title="Education"></asideTitle>

        <education class="padding" :lstEducation="education"></education>

        <asideTitle title="Professional Skills"></asideTitle>

        <professional class="padding" v-for="item in professionalSkill" :technology="item.technology" :percent="item.percent" :key="item.id"></professional>

      </div>
    </aside>

    <!--      HEADER    -->
    <header class="item s-100 m-65 l-75 to-right" :class="toggleMenu ? 'header in':'header'"  >
      <div :class="loading ? 'terminal min':'terminal max'">
        <div class="titleBar">
          <span class="titleBar__clo"></span>
          <span class="titleBar__max"></span>
          <span class="titleBar__min"></span>
        </div>
        <p class="terminal__text">{{commandName}}</p> 
        <h4 class="terminal__name" :class="name2 !== '' ? '':'' ">{{name2}}</h4>
        <!-- <p class="terminal__text">[root@linux /]# last name</p> -->
        <h4 class="terminal__last">{{last2}}</h4>
        <!-- <p class="terminal__text"></p> -->
        <!-- <h4 class="terminal__job">{{job}}</h4>   -->
      </div>      
      <!-- <span class="header__btnMax" @click="max = !max">
        
      </span> -->

      <!-- <social class="header__social" :socialItem="socialNetwork"></social>    -->
    </header>

    <!--      MAIN      -->
    <main class="item s-100 m-65 l-75 to-right" :class="toggleMenu ? 'main hide':'main in'">
      <div class="container">  
                    
        <contentVue class="item info" v-for="content in contents" :key="content.idContent" :title="content.title" :icon="content.icon" :contentText="content.contentText">
        </contentVue>        
      </div>
    </main>

    <footer class="footer item s-100 m-65 l-75 to-right no-padding" v-if="name != ''">    
      <p class="item">Website made with <img src="./assets/logo.png" alt="" class="vue__logo"> 
        <span class="net__logo"><svg xmlns="http://www.w3.org/2000/svg" width="25" height="25" viewBox="0 0 512 512"><g fill="#008cdb"><path d="M496 159.211H365.232v19.383h53.944v167.195h22.885V178.594H496zM343.163 178.594v-19.383h-99.94v186.578h99.94v-19.391h-77.058V261.25h68.654v-19.383h-68.654v-63.273zM48.227 336.68c0 8.898-7.212 16.109-16.109 16.109-8.902 0-16.117-7.211-16.117-16.109 0-8.906 7.215-16.109 16.117-16.109 8.896-.001 16.109 7.202 16.109 16.109zM217.232 159.211h-22.888v147.297L89.102 159.211H66.217v186.578h22.885V198.633L194.42 345.789h22.812z"/></g></svg></span>
      <img src="./assets/ed-grid.png" alt="" class="ed__logo"></p>    
  </footer>
  </div>
  <!-- <person></person> -->
</template>

<script>

import asideTitle from './components/AsideTitle.vue';
import contact from './components/Contact.vue';
import social from './components/Social.vue';
import education from './components/Education.vue';
import professional from './components/Professional.vue';
import contentVue from './components/Content.vue';

//Extarnal
import axios from 'axios';
export default {
  components: { asideTitle, contact, social, education, professional, contentVue },
  data() {
    return {
      loading: true,
      toggleMenu: false,
      name: '',        
      name2: '',    
      last: '',
      last2:  '',
      job: '',
      email: '',
      cell: '',      
      location: {},
      socialNetwork:[],
      education: [],
      professionalSkill: [],
      contents: [],
      commandName: '',
      max: false
    }
  },
  methods: {
    activeAside: () => {
      console.log('its works');
    },    
    writing() {  
      let arrFromStr = "Developer Frontend & Backend".split('');
      let i = 0;
      let arrFromStr2 = this.name.split('');
      let x = 0;      

      var textCommand  = setInterval(() => {        
        this.commandName += arrFromStr[i];
        i++;
        if (i === arrFromStr.length) {
          clearInterval(textCommand);          
          this.name2 = this.name;
          this.last2 = this.last;
          
        }
      }, 100);
      
    }
  },
  mounted() {
    //this.writing(this.name);
    console.log('Mounted');
    axios.get('http://bossinovations.com.stem.arvixe.com/api/Usuario/')
        .then((response) => {
          console.log('Response data: ' + response.data[0]);
          const data = response.data[0];
          this.name = data.name;
          this.last = data.last;
          this.email = data.email;
          this.cell = data.cell;   
          this.location = data.Locations[0];  
          this.socialNetwork = data.SocialNetworks;  
          this.education = data.Educations;
          this.professionalSkill = data.ProfessionalSkills;
          this.contents = data.Contents;
          this.loading = false;                    
          console.log('Ending loading');
          this.writing();
        })
        .catch((response) => {
          this.loading = false;
        });
  },
  created() {    
    console.log('Created')
  }
}
</script>

<style src="./styles/style.scss" lang="scss">

</style>
