<template>
  <header class="header">
    <div class="header__user">
      <h1 class="header__name">{{name}}</h1>
      
      <h2 class="header__last">{{last}}</h2>
    </div>        
  </header>  
</template>

<script>
export default {
  props: [ 'name', 'last' ],
  name: 'appHeader',
  data() {
    return {

    }
  }
}
</script>
