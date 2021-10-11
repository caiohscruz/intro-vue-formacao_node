<template>
    <div>
        <div v-for="(client,index) in clients" :key="client.id">
            <h4>{{index}}</h4>
            <Client :client="client" @Delete="Delete(index)"/>
            <hr>
            <h4>Edição:</h4>
            <input v-model="client.name">
            <br>
            <input v-model="client.age">
            <br>
            <input type="radio" :value="true" v-model="client.showEmail">
            <label for="Show">Show e-mail</label>
            <br>
            <input type="radio" :value="false" v-model="client.showEmail">
            <label for="Hide">Hide e-mail</label>
            <br>
        </div>
    </div>
</template>

<script>
    import Client from "./Client";

    export default {
        name: "ClientList",
        props:{
            clients: Array,
        },
        components: {
            Client,
        },
        methods:{
            Delete(index){
                this.clients.splice(index, 1);
            }
        }
    }
</script>

<style>

</style>