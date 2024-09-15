<script>
import AppCatchBtn from "./AppCatchBtn.vue";
import AppImages from "./AppImages.vue";
import AppSearch from "./AppSearch.vue";
import AppStats from "./AppStats.vue";

export default {
    components: {
        AppSearch,
        AppImages,
        AppStats,
        AppCatchBtn
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="p-3">
        <div class="d-flex justify-content-between">
            <AppSearch />
            <AppCatchBtn />
        </div>
        <AppImages />
        <AppStats />
    </div>
</template>

<style scoped lang="scss">

</style>