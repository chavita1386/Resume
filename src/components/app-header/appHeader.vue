<template>
  <header class="header">
    <app-social :social-list="socialList" :class="ready ? 'ready':''"></app-social>
    <div class="header__user">
      <h1 class="header__name" :class="ready ? 'ready':''"><span>{{name}}</span></h1>
      
      <h2 class="header__last" :class="ready ? 'ready':''"><span>{{last}}</span></h2>
    </div>        
  </header>  
</template>

<script>
import appSocial from '../app-social/appSocial.vue';
export default {
  props: [ 'name', 'last', 'socialList', 'ready' ],
  name: 'appHeader',
  components: {appSocial},
  data() {
    return {

    }
  }
}
</script>

<style lang="scss">
.header {
  background: #111B3F url('../../assets/bg.jpg') no-repeat center center;
  background-size: 145%;
}
</style>


