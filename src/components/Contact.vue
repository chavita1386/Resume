<template>
  <div class="contact">
    <ul class="list">
      <li class="list__li"><span>{{cell}}</span></li>
      <li class="list__li"><span><a :href="'mailto:'+ email">{{email}}</a></span></li>
      <li class="list__li"><span>{{location.city}}, {{location.state}}</span></li>
      <li class="list__li"><span>{{location.postcode}}</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['location', 'email', 'cell'],
  data() {
    return {

    }
  }
}
</script>


