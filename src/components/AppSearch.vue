<script>
import axios from 'axios';
import { store } from '@/store';

export default {
    data() {
        return {
            store,
        }
    },
    methods: {
        search() {
            // pokemon info
            axios
            .get(`https://pokeapi.co/api/v2/pokemon/${this.store.querySearch}/`)
            .then((resp)=>{
                this.store.info = resp.data
                console.log(this.store.info);
            })

            // pokemon habitat
            // axios
            // .get(`https://pokeapi.co/api/v2/pokemon-species/${this.store.querySearch}/`)
            // .then((resp)=>{
            //     this.store.habitat = resp.data.habitat.url
            //     console.log(this.store.habitat);
            // })
        }
    }
}

</script>

<template>
    <div class="group">
        <svg viewBox="0 0 24 24" aria-hidden="true" class="search-icon">
            <g>
                <path d="M21.53 20.47l-3.66-3.66C19.195 15.24 20 13.214 20 11c0-4.97-4.03-9-9-9s-9 4.03-9 9 4.03 9 9 9c2.215 0 4.24-.804 5.808-2.13l3.66 3.66c.147.146.34.22.53.22s.385-.073.53-.22c.295-.293.295-.767.002-1.06zM3.5 11c0-4.135 3.365-7.5 7.5-7.5s7.5 3.365 7.5 7.5-3.365 7.5-7.5 7.5-7.5-3.365-7.5-7.5z"></path>
            </g>
        </svg>

        <input
        id="query"
        class="input"
        type="search"
        placeholder="Search..."
        name="searchbar"
        autocomplete="off"
        v-model="this.store.querySearch"
        @keyup.enter="search"
        />
    </div>
</template>

<style scoped lang="scss">

.group {
    display: flex;
    line-height: 28px;
    align-items: center;
    position: relative;
    max-width: 190px;
}

.input {
    font-family: "Montserrat", sans-serif;
    width: 100%;
    height: 45px;
    padding-left: 2.5rem;
    box-shadow: 0 0 0 1.5px #2b2c37, 0 0 25px -17px #000;
    border: 0;
    border-radius: 12px;
    background-color: #ffffff;
    outline: none;
    color: #46474e;
    transition: all 0.25s cubic-bezier(0.19, 1, 0.22, 1);
    cursor: text;
    z-index: 0;
}

.input::placeholder {
    color: #46474e;
}

.input:hover {
    box-shadow: 0 0 0 2.5px #2f303d, 0px 0px 25px -15px #000;
}

.input:active {
    transform: scale(0.95);
}

.input:focus {
    box-shadow: 0 0 0 2.5px #2f303d;
}

.search-icon {
    position: absolute;
    left: 1rem;
    fill: #46474e;
    width: 1rem;
    height: 1rem;
    pointer-events: none;
    z-index: 1;
}

</style>
