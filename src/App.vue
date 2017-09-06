<template>
  <div>
    <header class="header">
      <h1 class="header__title">{{name}}</h1>      
    </header>
    <aside>
      Aside
    </aside>
    <main>
      Main
    </main>
  </div>
  <!-- <person></person> -->
</template>

<script>
// import person from './components/Person.vue';
// import cabeza from './components/Header.vue';
export default {
  // components:  { cabeza },
  data() {
    return {
      name: 'Salvador Rocha Robledo'
    }
  }
}
</script>

<style src="./styles/style.scss" lang="scss">

</style>
