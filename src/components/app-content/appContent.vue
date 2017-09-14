<template>
  <div class="content">
    <div class="content__in">
      <h2 class="content__title">{{title}}</h2>
      <div class="content__text" v-html="text"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title', 'text'],
  data() {
    return {}
  }
}
</script>
