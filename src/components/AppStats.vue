<script>
import { store } from '@/store';

export default {
    data() {
        return {
            store
        }
    },
    computed: {
        getStats() {
            if (!this.store.info || !this.store.info.stats) {
                return {};
            }
            return Object.fromEntries(
                Object.entries(this.store.info.stats)
            );

        }
    }
}
</script>

<template>
    <div class="p-2 pt-0">
        <div class="bg-success rounded p-3" style="height: 200px;">
            <h5 v-if="this.store.info" class="text-center text-uppercase fw-bold">{{ this.store.info.name }}</h5>
            <div v-for="item in getStats" class="d-flex">
                <div class="w-50">{{ item.stat.name }}</div>
                <!-- <div class="w-50">{{ item.base_stat }}</div> -->
                <div class="bg-secondary-subtle w-50 rounded align-self-center" style="height: 5px;">
                    <div class="h-100 bg-black rounded" :style="{width: item.base_stat / 2 + '%' }"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">

</style>