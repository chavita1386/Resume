<template>
  <div class="principal" :class="menu ? 'in':''" @scroll="handleScroll" > 
      <app-header :name="name" :last="last" :socialList="SocialNetworks" :ready="ready ? true : false" ></app-header>
      <main class="main" >
        <app-content v-for="item in contents" :key="item.idContent" :text="item.contentText" :title="item.title" :ready="ready" :scroll-top="scrollTop"></app-content>
      </main>
    </div>
</template>

<script>
import appHeader from '../app-header/appHeader.vue'
import appContent from  '../app-content/appContent.vue'
export default {
  components: { appHeader, appContent },
  props: ['SocialNetworks', 'name', 'last', 'ready', 'contents', 'menu'],
  data() {
    return {
      scrollTop: 0      
    }
  },
  mounted() {
    //this.elements = this.$el.childNodes;
  },
  methods: {
    handleScroll() {
      // console.log(this.$el.scrollHeight); 
      // console.log(this.$el.scrollTop); 
      // this.scrollHeight = this.$el.scrollHeight;
      this.scrollTop = this.$el.scrollTop;
      //console.log(document.body.scrollTop)
      //console.log(this.$el.children[2].scrollTop)
      //offsetTop h2 770
      // 827
    }   
  }  
}
</script>

