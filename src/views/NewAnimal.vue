<template>
    <section>
        <h2>Добавление нового животного</h2>
        <form @submit.prevent="addAnimal">
            <input type="text" v-model.trim="name">
            <input type="submit" value="Добавить">
        </form>
    </section>
</template>

<script>
    import axios from "axios";

    export default {
        name: "NewAnimal",
        data: function() {
            return {
                name: ''
            }
        },
        methods: {
            addAnimal: function () {
                const fd = new FormData();
                fd.append('name', this.name);
                console.log(this.name);
                axios
                    .post('http://shelter/api/add/animal', fd)
                    .then(response => {
                        console.log(response.data)
                    });
            }
        }

    }

</script>

<style scoped>

</style>