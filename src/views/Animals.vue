<template>
    <section>
        <h2>Список животных</h2>
        <div v-for="(animal, i) in animals" :key="i">
            <h2>{{animal.animal_name}}</h2>
            <p>Возраст: {{ animal.age }}</p>
            <p>Категория: {{ animal.description }}</p>
            <hr>
        </div>

    </section>
</template>

<script>
    import axios from "axios";

    export default {
        name: "Animals",
        data: function() {
            return {
                animals: []
            }
        },
        created() {
            axios
                .get('http://shelter/api/animals')
                .then(response => {
                    this.animals = response.data;
                    console.log(this.animals)
                });
        }
    }
</script>

<style scoped>

</style>