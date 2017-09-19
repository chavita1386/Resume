<template>
  <span :class="css"></span>
</template>

<script>
export default {
  props: ['parent','icon'],
  data() {
    return {

    }
  },
  computed: {
    css() {
      return this.parent + ' battery--' + this.icon;
    }
  }
  
}
</script>

