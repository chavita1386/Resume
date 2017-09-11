<template>
  <div class="social">
    <ul class="">
      <linkList v-for="social in socialItem" :key="social.idSolicalNetwork" :name="social.name" :url="social.url" ></linkList>      
    </ul>
  </div>
</template>

<script>
import linkList from './subComponents/LinkList.vue';
export default {  
  props: ['socialItem'],
  components: { linkList },
  data() {
    return {
    }
  },
  mounted() {
    //console.log(this.socialItem);
  },
  computed: {
    cssClasses: function(name) {
      return 'list__ico list__ico--' + name;
    }
  }
}
</script>
