<script>
import { store } from '@/store';

export default {
    data() {
        return {
            store
        }
    },
    methods: {
        capture() {
            this.store.captured.indexOf(this.store.info.name) === -1? this.store.captured.push(this.store.info.name) : console.log('You already captured this pokemon');
        }
    }
}
</script>

<template>
    <div>
        <button @click="capture">Catch it!</button>
    </div>
</template>

<style scoped lang="scss">

</style>