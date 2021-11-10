<template>
  <div class="flex flex-col">
    <h1 class="text-center text-5xl font-thin">Vue Form Demonestration</h1>
    <Form />
  </div>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: { Form },
}
</script>
