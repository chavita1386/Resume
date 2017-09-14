<template>
  <li class="social__item">
        <a href="#" class="social__link">        
          <span :class="css"></span>
          <span class="social__name">{{name}}</span>
        </a>
  </li>
</template>

<script>
export default {
  props: [ 'name', 'url' ],
  data() {
    return {
      
    }
  },
  computed: {
    css() {
      console.log(this);
      return 'icon-' + this.name + '-square';
    }
  }
}
</script>
