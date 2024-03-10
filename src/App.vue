<script>
import MainPage from './components/MainPage.vue';
import AnswerPage from './components/AnswerPage.vue';
import Modal from './components/Modal.vue';

export default {
    components: {
        MainPage,
        AnswerPage,
        Modal
    },
    data() {
        return {
            showAnswerPage: false,
            showModal: false,
            result: {
                fullName: '',
                age: '',
                experience: '',
                knowledge: '',
                salary: '',
            },
        }
    },
    methods: {
        parseResult(result) {
            this.result = result;
            this.showModal = false;
            this.showAnswerPage = true;
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="header">
            <button @click="showAnswerPage = false">Показать кнопку</button>
            <button @click="showAnswerPage = true">Показать результат</button>
        </div>
        <div class="content">
            <Modal v-if="showModal" @close="showModal = false" @submit="parseResult" :form="result"></Modal>
            <MainPage v-if="!showAnswerPage" @start="showModal = true"></MainPage>
            <AnswerPage v-else :result="result"></AnswerPage>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.header {
    display: flex;
    justify-content: center;
    gap: 100px;
    align-items: center;
}

button {
  padding: 10px 22px;
  border: none;
  font-size: 14px;
  border-radius: 30px;
  outline: none;
  color: #FFFFFF;
  background: rgba(54, 106, 243, 1);
  cursor: pointer;
}
</style>
