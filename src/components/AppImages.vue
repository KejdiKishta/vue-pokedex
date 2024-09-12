<script>
import { store } from "@/store";

export default {
    data() {
        return {
            store,
        };
    },
    computed: {
        filteredSprites() {
            if (!this.store.info || !this.store.info.sprites) {
                return {};
            }
            return Object.fromEntries(
                Object.entries(this.store.info.sprites)
                    .filter(([key, value]) => typeof value === 'string' && key.includes('default'))
            );
        }
    }
};
</script>

<template>
    <div class="p-5">
        <div class="w-75 m-auto ratio ratio-16x9 ms_bg">>
            <!-- Controlla se store.info e store.info.sprites sono validi -->
            <div v-if="store.info && store.info.sprites" id="carousel" class="carousel slide carousel-fade">
                <div class="carousel-inner">
                    <div
                        v-for="(image, key) in filteredSprites"
                        :key="key"
                        class="carousel-item"
                        :class="{'active': key === 'front_default'}"
                    >
                        <img :src="image" class="d-block w-50 m-auto" alt="Image" />
                    </div>
                </div>
                <!-- Controlli di navigazione -->
                <button class="carousel-control-prev" type="button" data-bs-target="#carousel" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#carousel" data-bs-slide="next">
                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Next</span>
                </button>
            </div>
            <!-- Messaggio di fallback -->
            <p v-else>Nessuna immagine disponibile</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
.ms_bg {
    background-image: url(../assets/516813.jpg);
    background-size: cover;
}
</style>
