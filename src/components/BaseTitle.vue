<template>
    <h1>
        <slot />
    </h1>
</template>

<script>
export default {
  name: 'BaseTitle'
}
</script>

<style lang="scss" scoped>

h1 {
    color:green;
    font-size: 40px;
}
</style>
