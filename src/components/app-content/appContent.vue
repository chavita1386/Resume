<template>
  <div class="content">
    <div class="content__in">
      <h2 class="content__title" :class="ready ? 'in':''"><span>{{title}}</span></h2>
      <div class="content__text" v-html="text"></div>
    </div>          
  </div>
</template>

<script>
export default {
  props: ['title', 'text', 'ready', 'scrollTop'],
  data() {
    return {}
  }
}
</script>
