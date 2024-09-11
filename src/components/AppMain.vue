<script>
import AppLeftCol from './AppLeftCol.vue';

export default {
    components: {
        AppLeftCol,
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <main class="d-flex justify-content-center align-items-center">
        <div class="w-75 ratio ratio-21x9 bg-danger">
            <AppLeftCol />
        </div>
    </main>
</template>

<style scoped lang="scss">
@use "../scss/partials/variables" as *;

main {
    height: 100vh - $header-height;
    overflow: hidden;
}
</style>