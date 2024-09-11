<script>
import AppImages from "./AppImages.vue";
import AppSearch from "./AppSearch.vue";
import AppStats from "./AppStats.vue";

export default {
    components: {
        AppSearch,
        AppImages,
        AppStats
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="p-3">
        <AppSearch />
        <AppImages />
        <AppStats />
    </div>
</template>

<style scoped lang="scss">

</style>