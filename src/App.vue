<template>
  <div id="app">
    <FormClient :clients="clients"/>
    <hr>
    <ClientList :clients="orderClients"/>
  </div>
</template>

<script>
  import ClientList from "./components/ClientList";
  import FormClient from "./components/FormClient";
  import _ from "lodash";
  
  export default {
    name: 'App',
    components: {
      FormClient,
      ClientList
    },
    data() {
      return {
        clients: [{
            id: 1,
            name: "Caio",
            age: 28,
            email: "caio@teste.com",
            showEmail: false,
            isPremium: true
          },
          {
            id: 2,
            name: "Pedro",
            age: 27,
            email: "pedro@teste.com",
            showEmail: true,
            isPremium: false
          },
          {
            id: 3,
            name: "Cristiano",
            age: 26,
            email: "cristiano@teste.com",
            showEmail: true,
            isPremium: true
          },
        ]
      }
    },
    computed:{
      orderClients(){
        return _.orderBy(this.clients, ["name"],["asc"]);
      }
    }
  }
</script>

<style>

</style>