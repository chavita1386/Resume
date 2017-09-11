<template>
  <div class="item info">
    <contentTitle :title="title" :icon="icon"></contentTitle>
    <!-- <h2 class="info__title">{{title}}</h2> -->
    <div v-html="contentText"></div>
  </div>
</template>

<script>
import contentTitle from './subComponents/ContentTitle.vue';

export default {
  props: ['title', 'contentText', 'icon'],
  components: { contentTitle },
  data() {
    return {

    }
  }
}
</script>

