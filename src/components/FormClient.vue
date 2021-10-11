<template>
    <div>
        <h3>Cadastro</h3>
        <input type="text" placeholder="name" v-model="nameField">
        <br>
        <input type="email" placeholder="email" v-model="emailField">
        <br>
        <input type="number" placeholder="age" v-model="ageField">
        <br>
        <input type="radio" :value="true" v-model="isPremiumField">
        <label for="Show">Premium</label>
        <br>
        <input type="radio" :value="false" v-model="isPremiumField">
        <label for="Hide">Not Premium</label>
        <br>
        <input type="radio" :value="true" v-model="showEmailField">
        <label for="Show">Show e-mail</label>
        <br>
        <input type="radio" :value="false" v-model="showEmailField">
        <label for="Hide">Hide e-mail</label>
        <br>
        <button @click="RegisterClient">Cadastrar</button>
    </div>
</template>

<script>
    export default {
        name: "ClientList",
        props: {
            clients: Array,
        },
        data() {
            return {
                nameField: "",
                ageField: "",
                emailField: "",
                isPremiumField: false,
                showEmailField: true,
            }
        },
        methods: {
            RegisterClient() {
                this.clients.push({
                    id: Date.now(),
                    name: this.nameField,
                    age: this.ageField,
                    email: this.emailField,
                    showEmail: this.showEmailField,
                    isPremium: this.isPremiumField
                });
                this.nameField = "";
                this.ageField = "";
                this.emailField = "";
                this.isPremiumField = false;
                this.showEmailField = true;
            }
        }
    }
</script>

<style>

</style>