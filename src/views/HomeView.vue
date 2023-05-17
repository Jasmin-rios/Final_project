<script>
import header_bar from '../components/header_bar.vue'
import searching_bar from '../components/searching_bar.vue';
import categories from '../components/categories.vue';
import events from '../components/events.vue';
// import footer_bar from '../components/footer_bar.vue';

export default{
  name: 'Home',
  components:{
    header_bar, searching_bar, categories, events,
  }}
</script>

<template>
  <main>
<header_bar />
<searching_bar/>
<categories/>
<events />
<!--<footer_bar /> -->
  </main>
</template>

