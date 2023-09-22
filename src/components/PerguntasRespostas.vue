<template>  
    <div>
      <form @submit.prevent="gerarResposta">
        <label for="pergunta">Faça uma pergunta:</label>
        <input type="text" id="pergunta" v-model="question" required>
        <button type="submit">Gerar Resposta</button>
      </form>
  
      <div v-if="answer">
        <p><strong>Sua Pergunta:</strong> {{ question }}</p>
        <p><strong>Resposta:</strong> {{ answer }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        question: '',
        answer: ''
      };
    },
    methods: {
      gerarResposta() {
        const respostas = [
          'Com certeza',
          'É... não tenho certeza!',
          'Claro que não',
          'Acho difícil',
          'Possivelmente não'
        ];
        const indiceAleatorio = Math.floor(Math.random() * respostas.length);
        this.answer = respostas[indiceAleatorio];
      }
    }
  };
  </script>
  