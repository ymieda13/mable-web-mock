<template>
  <section class="container">
    <div>
      <preview-map/>
    </div>
  </section>
</template>

<script>
import PreviewMap from '~/components/Map.vue'

export default {
  layout: 'default',
  components: {
    PreviewMap
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
