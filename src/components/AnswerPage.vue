<template>
    <div class="result">
        <div class="result_in_text">
            <p v-for="(key, value) in result" :key="key">
                {{ translate[value] }}: {{ result[value] }}
            </p>
        </div>
        <div class="result_in_json">
            {{ JSON.stringify(result) }}
        </div>
    </div>
</template>

<script>
export default {
    name: "AnswerPage",
    props: {
        result: Object
    },
    data() {
        return {
            translate: {
                fullName: 'Ф.И.О.',
                age: 'Возраст',
                experience: 'Опыт работы',
                knowledge: 'Стек знаний',
                salary: 'Зарплатные ожидания',
            }
        }
    },
}
</script>

<style scoped>
.result {
    border: 2px solid black;
    border-radius: 10px;
    position: fixed;
    top: 40px;
    left: 40px;
    z-index: -10;
    display: flex;
    flex-direction: row;
    gap: 20px;
}
</style>