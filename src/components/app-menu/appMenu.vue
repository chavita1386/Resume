<template>
  <div class="menu">
    <a href="#" class="menu__link icon-notebook-streamline" @click.prevent="toggleMenu"></a>
  </div>
</template>

<script>
export default {
  data() {
    return {

    }
  },
  methods: {
    toggleMenu() {
      console.log('Menu toggleMenu');
      this.$emit('showMenu');
    }
  }
}
</script>

