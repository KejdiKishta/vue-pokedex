<script>
import AppLeftCol from './AppLeftCol.vue';
import AppRightCol from './AppRightCol.vue';

export default {
    components: {
        AppLeftCol,
        AppRightCol,
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <main class="d-flex justify-content-center align-items-center">
        <div class="w-75 bg-danger d-flex">
            <div class="w-50">
                <AppLeftCol />
            </div>
            <div class="w-50">
                <AppRightCol />
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use "../scss/partials/variables" as *;

main {
    height: calc( 100vh - $header-height);
    overflow: hidden;
}
</style>