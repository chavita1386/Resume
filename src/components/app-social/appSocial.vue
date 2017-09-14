<template>
  <div class="social">
    <ul class="social_list">
      <app-list-item v-for="item in socialList" :key="item.idSocialNetwork" :name="item.name" :url="item.url"></app-list-item>   
    </ul>
  </div>
</template>

<script>
import appListItem from './appListItem.vue';
export default {
  props: ['socialList'],  
  components: { appListItem },  
  data() {
    return {

    }
  },
  computed: {
    css:function()  {
      return this.socialList.name;
    }
  }
}
</script>
