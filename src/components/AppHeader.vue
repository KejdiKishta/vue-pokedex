<script>

</script>

<template>
    <header>
        <img src="../assets/pokedex-3d-logo.png" alt="">
    </header>
</template>

<style scoped lang="scss">
@use "../scss/partials/variables" as *;

header {
    background-image: url('../assets/516813.jpg');
    background-size: contain;
    height: $header-height;
    text-align: center;

    img {
        max-height: 100%;
    }
}
</style>