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
            this.store.captured.indexOf(this.store.info.name) === -1? this.store.captured.push(this.store.info.name) : console.log("You've already captured this pokemon");
        }
    }
}
</script>

<template>
    <div>
        <button class="rounded-4 px-3" @click="capture">Catch it!</button>
    </div>
</template>

<style scoped lang="scss">
button {
    border: 1px solid black;
    height: 100%;
}
</style>