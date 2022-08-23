<script>
import axios from 'axios';

  export default {
    data: function () {
      return {
        message: "Welcome to Vue.js!",
        contacts: []
      };
    },
    created: function () {},
    methods: {
      indexContacts: function() {
        console.log('getting the data');
        axios.get("http://localhost:3000/contacts.json").then(response => { console.log(response.data);
        this.contacts = response.data;
        })
      }

    },

  };
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="contact in contacts">
   <p>{{ contact }}</p>
   <br />
   </div>
   <button v-on:click="indexContacts()">Get Contacts</button>
  </div>
</template>

<style></style>