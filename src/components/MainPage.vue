<template>
    <div class="main">
        <button class="beginButton" @click="$emit('start')">Начать</button>
    </div>
</template>

<script>
    export default {
        name: "MainPage",
        emits: ["start"],
    }
</script>

<style scoped>
.main {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100dvh;
}
.beginButton {
  width: 200px;
  height: 48px;
  border: none;
  font-size: 18px;
  border-radius: 30px;
  outline: none;
  color: #FFFFFF;
  background: #32BCA3;
  cursor: pointer;
}
.beginButton:hover {
  background: #26ac93; 
}
</style>