<template>
  <a :href="url">
      {{ text }}
  </a>
</template>

<script>
export default {
    name: 'MenuLink',
    props: ['url', 'text'],
}
</script>

<style>
    
</style>