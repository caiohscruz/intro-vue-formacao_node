<template>
  <div class="client" :class="{'premium': client.isPremium}">
    <h4>Name: {{client.name}} <span v-if="client.isPremium == true">[Premium]</span></h4>
    <hr>
    <p>Age: {{client.age}}</p>
    <p v-if="client.showEmail == true">E-mail: {{client.email | processEmail}}</p>
    <p v-else>E-mail escondido</p>
    <button @click="ChangePremium(client)">
      <span v-if="client.isPremium == true">Remove Premium</span>
      <span v-else>Make Premium</span>
    </button>
    <button @click="Delete(client)">Deletar</button>
  </div>
</template>

<script>
  export default {
    name: 'Client',
    props: {
      client: Object
    },
    methods: {
      ChangePremium(client) {
        client.isPremium = !client.isPremium
      },
      Delete() {
        this.$emit("Delete", );
      }
    },
    filters: {
      processEmail(value) {
        return value.toUpperCase();
      }
    }

  }
</script>

<style scoped>
  .client {
    background-color: rgba(235, 165, 165, 0.562);
    padding: 1%;
    margin-top: 2%;
    width: 100%;
    height: 100%;
  }

  .premium {
    background-color: rgba(0, 0, 0, 0.562);
    color: gold;
  }
</style>