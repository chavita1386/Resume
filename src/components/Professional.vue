<template>
  <div class="professional">
    <div class="professional__title">
      <label>
        {{technology}}
      </label>
      <span>

      </span>
    </div>
    <div :class="css">

    </div>
  </div>
</template>

<script>
export default {
  props: ['technology', 'percent'],
  data() {
    return {

    }
  },
  computed: {
    css() {
      return 'level-' + this.percent;
    }
  }

}
</script>

