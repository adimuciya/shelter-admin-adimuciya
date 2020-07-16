<template>
    <section>
        <h2>Список животных</h2>
        <div v-for="(animal, i) in animals" :key="i">
            <h2>{{animal.animal_name}}</h2>
            <p>Возраст: {{animal.age}}</p>
            <p>Категория: {{animal.description}}</p>
        </div>
    </section>
</template>

<script>
    import axios from "axios";
    export default {
        name: "Animals",
        data: function(){
          return {
              animals: []
          }
        },
        created() {
        // сработает при открытии странички
        //    http://shelter - адрес (ip) сервера
        //    /api/animals -  строка запроса
            axios
                .get('http://shelter/api/animals')
                .then(response => {
                    this.animals = response.data;
                    console.log(response.data);
                })
        }
    }
</script>

<style scoped>

</style>