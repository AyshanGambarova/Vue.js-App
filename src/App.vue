<template>
  <div>
    <h1>Create contact</h1>
    <div id="form">
      <div>
        <label>Name and Surname:</label>
        <input type="text" v-model="name" />
      </div>
      <br />
      <div>
        <label>Phone:</label>
        <input type="text" v-model="phone" />
      </div>
      <br />
      <div>
        <button @click="handleSubmit">Save</button>
      </div>
    </div>
    <br />
    <br />
    <ContactList :data="contacts" @delete="deleteContact"></ContactList>
  </div>
</template>

<script>
import ContactList from "./components/ContactList.vue";
export default {
  name: "App",
  data() {
    return {
      name: "",
      phone: "",
      contacts: [],
    };
  },
  methods: {
    handleSubmit() {
      this.contacts.push({ name: this.name, phone: this.phone });
      this.name = "";
      this.phone = "";
    },
    deleteContact(index) {
      this.contacts.splice(index, 1);
    },
  },
  components: { ContactList },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
