<template>
  <div class="education__card">
    <h4>{{title}}</h4>
    <h5>{{school}}</h5>
    <span class="icon-calendar"></span>
    <span>{{time}}</span>
  </div>
</template>

<script>
export default {
  props: ['title', 'school', 'time'],
  data() {
    return {

    }
  }
}
</script>

