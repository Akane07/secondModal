<template>
    <div class="container">
        <div class="modal">
            <div class="header">
                <p>Форма</p>
                <img src="../assets/close.svg" alt="close" class="close" @click="$emit('close')"/>
            </div>
            <div class="contnet">
                <div class="field">
                    <label for="fullname">Ф.И.О.</label>
                    <input type="text" name="fullname" v-model="clearForm.fullName">
                </div>

                <div class="field">
                    <label for="age">Возраст</label>
                    <input type="number" name="age" v-model="clearForm.age">
                </div>

                <div class="field">
                    <label for="experience">Опыт работы</label>
                    <input type="text" name="experience" v-model="clearForm.experience">
                </div>

                <div class="field">
                    <label for="knowledge">Стек знаний</label>
                    <input type="text" name="knowledge" v-model="clearForm.knowledge">
                </div>

                <div class="field">
                    <label for="salary">Зарплатные ожидания</label>
                    <input type="text" name="salary" v-model="clearForm.salary">
                </div>
            </div>
            <div class="submitButton">
                <button @click="submit">Отправить</button>
            </div>
        </div>
    </div>
</template>

<script>
import { toRaw } from "vue";

export default {
    name: "Modal",
    emits: ['close'],
    props: {
        form: Object
    },
    data() {
        return {
            clearForm: structuredClone(toRaw(this.form))
        }
    },
    methods: {
        submit() {
            this.$emit('submit', this.clearForm)
        }
    },
}
</script>

<style scoped>
.container {
  position: fixed;
  top: 0;
  height: 100dvh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.2);
}

.modal {
  max-width: 500px;
  min-width: 250px;
  background: white;
  box-shadow: 0px 8px 32px 0px rgba(0, 0, 0, 0.16);
  padding: 20px;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.header {
  display: flex;
  justify-content: space-between;
  width: 100%;
}
.contnet {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}
.close {
  cursor: pointer;
}
.field {
  display: flex;
  flex-direction: column;
}
.field input {
  border-radius: 5px;
  border: 1px solid rgb(163, 159, 159);
}
.submitButton button {
  padding: 10px 22px;
  border: none;
  font-size: 14px;
  border-radius: 30px;
  outline: none;
  color: #FFFFFF;
  background: rgba(54, 106, 243, 1);
  cursor: pointer;
}

.submitButton button:hover {
  background: rgb(37, 89, 221);
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

</style>