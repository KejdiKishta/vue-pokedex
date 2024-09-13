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
        <div class="bg-success p-3" style="height: 200px;">
            <div v-for="item in getStats" class="d-flex">
                <div class="w-50">{{ item.stat.name }}</div>
                <div class="w-50">{{ item.base_stat }}</div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">

</style>