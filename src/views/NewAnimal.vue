<template>
    <section>
        <h2>Добавление нового животного</h2>
        <form>
            <div>
                <label>
                    Категория:
                    <select v-model="id_category">
                        <option value="2">Собаки</option>
                        <option value="1">Кошки</option>
                    </select>
                </label>
            </div>
            <div>
                <label>Имя животного:
                    <input type="text" v-model.trim="animal_name">
                </label>
            </div>
            <div>
                <label>Описание животного:
                    <textarea v-model.trim="description"></textarea>
                </label>
            </div>
            <div>
                <label>Возраст животного:
                    <input type="number" v-model.trim="age">
                </label>
            </div>
            <div>
                <label>Документы:
                    <input type="checkbox" value="true" v-model="passport">
                </label>
            </div>
            <div>
                <label>Прививки:
                    <input type="checkbox" value="true" v-model="vaccination">
                </label>
            </div>
            <input type="submit" value="Добавить">
        </form>
    </section>
</template>

<script>
    export default {
        name: "NewAnimal",
        data: function() {
            return {
                id_category: null,
                animal_name: '',
                description: '',
                age: 0,
                passport: false,
                vaccination: false
            }
        }
    }

</script>

<style scoped>

</style>