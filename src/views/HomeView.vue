<script>
import header_bar from '../components/header_bar.vue'
import searching_bar from '../components/searching_bar.vue';
import events from '../components/events.vue';
import footer_bar from '../components/footer_bar.vue';

export default{
  name: 'Home',
  components:{
    header_bar, searching_bar, events, footer_bar
  }}
</script>

<template>
  <main>
<header_bar />
<searching_bar/>
<events />
<footer_bar />
  </main>
</template>

