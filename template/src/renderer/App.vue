<template>
  <div id="app">
    {{#isEnabled plugins 'vue-router'}}
    <router-view></router-view>
    {{else}}
    <landing-page></landing-page>
    {{/isEnabled}}
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
{{#isEnabled plugins 'vue-router'}}
{{else}}
  import LandingPage from '@/components/LandingPage.vue'

{{/isEnabled}}
  export default Vue.extend({
    name: '{{ name }}'{{#isEnabled plugins 'vue-router'}}{{else}},{{/isEnabled}}
{{#isEnabled plugins 'vue-router'}}
{{else}}
    components: {
      LandingPage
    }
{{/isEnabled}}
  })
</script>

<style>
  /* CSS */
</style>
