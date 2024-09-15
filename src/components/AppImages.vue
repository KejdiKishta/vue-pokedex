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
    <div class="pokedex-container my-4">
        <div class="pokedex-screen">
            <div v-if="store.info && store.info.sprites" id="carousel" class="carousel carousel-fade">
                <div class="carousel-inner">
                    <div
                        v-for="(image, key) in filteredSprites"
                        :key="key"
                        class="carousel-item"
                        :class="{'active': key === 'front_default'}"
                    >
                        <img :src="image" class="w-100 pokeball-image" alt="Image" />
                    </div>
                </div>
                <button class="carousel-control-prev" type="button" data-bs-target="#carousel" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#carousel" data-bs-slide="next">
                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Next</span>
                </button>
            </div>
            <p v-else>No valid Pokémon selected!</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
.pokedex-container {
    background-color: grey;
    border: 5px solid #000;
    border-radius: 10px;
    padding: 20px;
    width: 400px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
}

.pokedex-screen {
    background-color: #f0f0f0;
    border: 2px solid #000;
    padding: 10px;
    width: 100%;
    text-align: center;
}

.pokeball-image {
    max-width: 150px;
    margin: 0 auto;
}

.carousel-control-prev-icon,
.carousel-control-next-icon {
    filter: invert(100%);
}

</style>
