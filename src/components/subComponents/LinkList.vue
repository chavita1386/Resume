<template>
<li class="list__li">
    <a :href="url" class="list__link" target="_blank">
    <span :class="css"></span><span>{{name}}.com/srocha</span>
  </a>
</li>
</template>

<script>
export default {
  props: ['url', 'name'],
  data() {
    return {

    }
  },
  computed: {
    css() {
      return 'list__ico icon-' + this.name + '-square';
    }
  }
}
</script>

