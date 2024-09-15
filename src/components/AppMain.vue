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
    <main class="d-flex justify-content-start align-items-center">
        <div class="ms-5 rounded d-flex">
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
    background-image: url('../assets/3907402.png');
    background-size: cover;
    background-position: bottom;
    
    &>div {
        background-color: #C62828;
        border: 10px solid #8E0000;
        width: 60%;
    }
}
</style>