<template>
    <div class="d-flex selezione-categoria">
        <div class="form-floating">
            <select class="form-select-sm" aria-label=".form-select-sm example">
                <option selected>Seleziona Categoria</option>
                <option value="1">Massacro</option>
                <option value="2">Action</option>
                <option value="3">Fantasy</option>
            </select>
        </div>
    </div>
    <div class="container">
        <div class=" py-5">
            <div class="row d-flex g-5">
                <div class="mia-col"
                    v-for="(listaRickeMortHTML, i) in store.rickEmorty">
                    <div class="card h-100 p-2">
                        <img :src="listaRickeMortHTML.image" class="card-img-top" alt="...">
                        <div class="card-body">
                            <h5 class="card-title">{{ listaRickeMortHTML.name }}</h5>
                            <p class="card-text">{{ listaRickeMortHTML.status }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>


<script>
import axios from "axios";

import { store } from "../store.js"

export default {
    data() {
        return {
            // rickEmorty: [],
            store
        };
    },
    methods: {},
    beforeMount() { },
    mounted() {

        axios.get("https://rickandmortyapi.com/api/character")
            .then(resp => {
                console.log(resp);
                this.store.rickEmorty = resp.data.results

            })

    },
}
</script>

<style scoped>
.card {
    background-color: #2E3A46;
    color: white;
}

.mia-col {
    width: calc(100%/5);
}

.selezione-categoria {
    border-radius: 0;
    padding: .3rem 1rem;
    position: relative;
    bottom: 50px;
    left: -28px;
}
</style>