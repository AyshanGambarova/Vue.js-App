<template>
   <div>
    <div v-for="(contact,index) in data" :key="index">
   <div> {{contact.name}}-{{contact.phone}}-#{{index}} <button @click="removeContact(index)">Remove</button></div>
    </div>
   </div>
</template>
<script>
export default {
    props:['data'],
    name: "ContactList",
    methods:{
        removeContact(){
            this.$emit('delete');
        }
    }
}

</script>
<style>

</style>