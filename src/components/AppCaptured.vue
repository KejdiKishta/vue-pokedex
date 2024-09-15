<script>
import { store } from '@/store';

export default {
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class=" w-100 h-100 bg-white p-4">
        <div>My pokemons</div>
        <ul>
            <li v-for="capture in this.store.captured">{{ capture }}</li>
        </ul>
    </div>
</template>

<style scoped lang="scss">

</style>