<template>
  <div class="item info">
          <h2 class="info__title">{{title}}</h2>
          <div v-html="contentText"></div>
        </div>
</template>

<script>
export default {
  props: ['title', 'contentText'],
  data() {
    return {

    }
  }
}
</script>

