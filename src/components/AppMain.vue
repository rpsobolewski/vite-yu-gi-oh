<template>
    <main class="py-3">
        <div class="container bg-white">
            <div class="row p-2">
                <div class="col-3 p-1" v-for=" card  in   state.cards  " v-show="card.archetype === 'Alien'">
                    <div class="card  h-100">
                        <div class="card-header p-0">
                            <img class="w-100" :src='card.card_images[0].image_url' alt="">
                        </div>
                        <div class="card-body d-flex flex-column justify-content-center align-items-center p-1">
                            <div class="card_data text-center">
                                <p>{{ card.name }}</p>
                                <span>{{ card.archetype }}</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import { state } from './state.js'
export default {
    name: 'AppMain',
    data() {
        return {
            state
        }
    },
    created() {
        state.fetchData();
    }
}
</script>

<style lang="scss" scoped>
@use '../src/assets/scss/partials/variables' as *;

main {
    background: $ygo__bg;
}
</style>