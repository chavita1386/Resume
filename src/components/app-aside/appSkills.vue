<template>
  <div class="skills">
    <div class="skills__item" v-for="item in skills" :key="item.idProfessionalSkill">
      <label>{{item.technology}}</label>
      <app-icon :parent="iconParent" :icon="item.percent"></app-icon>
    </div>
  </div>
</template>

<script>
import appIcon from './appIcon.vue'; 
export default {
  props: ['skills'],
  components: { appIcon },
  data() {
    return {
      iconParent: 'battery'
    }
  },
  computed: {
    css() {
      return 'battery battery-low'
    }
  },
  mounted() {

  }
}
</script>

