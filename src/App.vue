<template>
  <div id="app">

    <app-social :social-list="data.SocialNetworks"></app-social>
    <app-header :name="data.name" :last="data.last"></app-header>

    <main class="main">
      <app-content v-for="item in data.Contents" :key="item.idContent" :text="item.contentText" :title="item.title"></app-content>
    </main>

    <code v-text="data">

    </code>
  </div>
</template>

<script>

import moment from 'moment';
import axios from 'axios';
import appHeader from './components/app-header/appHeader.vue';
import appSocial from './components/app-social/appSocial.vue';
import appContent from './components/app-content/appContent.vue';

export default {
  name: 'app',
  components: { appHeader, appSocial, appContent },
  data() {
    return {
      msg: 'Resume',
      data: ''
    }
  },
  mounted() {
    console.warn('Created: ' + moment().format('HH:mm:ss'));
    axios.get('http://bossinovations.com.stem.arvixe.com/api/Usuario/2')
      .then((response) => {
        console.log(response.data);
        this.data = response.data;
        console.warn('data:' + moment().format('HH:mm:ss'));
      })
      .catch((response) => {
        console.log(reponse);
      });
  }
}
</script>

<style lang="scss" src='./scss/app.scss'>

</style>
