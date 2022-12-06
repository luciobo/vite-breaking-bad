<template>
    <div class="container">
        <div class=" py-5">
            <div class="row d-flex g-5">
                <div class="col-2 col"
                    v-for="(listaRickeMortHTML, i) in rickEmorty">
                    <div class="card h-100">
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


export default {
    data() {
        return {
            rickEmorty: []
        };
    },
    methods: {},
    beforeMount() { },
    mounted() {

        axios.get("https://rickandmortyapi.com/api/character")
            .then(resp => {
                console.log(resp);
                this.rickEmorty = resp.data.results

            })

    },
}
</script>

<style scoped>
.card {
    background-color: #2E3A46;
    color: white;
}

</style>