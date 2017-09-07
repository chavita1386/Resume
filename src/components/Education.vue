<template>
  <div class="education">
    <div class="education__cont" v-for="item in lstEducation" v-bind:key="item.idEducation">
      <h4 class="education__title" >
          {{item.title}}
      </h4>
      <p class="education__school">
          {{item.school}}
      </p>
      <span class="education__time">
          {{item.time}}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['lstEducation'],
  data() {
    return {

    }
  }
}
</script>

