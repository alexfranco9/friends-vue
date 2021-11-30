<template>
    <form @submit.prevent="submitData">
        <div>
            <label for="name">Name</label>
            <input type="text" v-model="enteredName">
        </div>
        <div>
            <label for="phone">Phone</label>
            <input type="text" v-model="enteredPhone">
        </div>
        <div>
            <label for="email">E-Mail</label>
            <input type="text" v-model="enteredEmail">
        </div>
        <div>
            <button>Add Contact</button>
        </div>
    </form>
</template>

<script>
export default {
    emits: ['add-contact'],
    data() {
        return {
            enteredName: '',
            enteredPhone: '',
            enteredEmail: ''
        };
    },
    methods: {
        submitData() {
            this.$emit('add-contact', this.enteredName, this.enteredName, this.enteredEmail)
        }
    }
};
</script>