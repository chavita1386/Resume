<template>
    <h2 class="info__title">
      <p :class="css"></p>
      {{title}}
    </h2>
</template>

<script>
export default {
  props: ['title', 'icon'],  
  data() {
    return {

    }
  },
  computed: {
    css() {
      return "icon-" + this.icon;
    }
  }
}
</script>
