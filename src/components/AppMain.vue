<script>
</script>

<template>
    <main class="d-flex justify-content-center align-items-center">
        <div class="w-75 ratio ratio-21x9 ms_pokedex bg-danger"></div>
    </main>
</template>

<style scoped lang="scss">
@use "../scss/partials/variables" as *;

main {
    height: 100vh - $header-height;
    overflow: hidden;
    // .ms_pokedex {
    //     height: 400px;
    //     width: 800px;
    // }
}
</style>