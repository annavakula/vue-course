<template>
    <div class="form">
        <h2>Message: {{ message }}</h2>
        <form @submit.prevent="submitForm">
         <label for="name">Name:</label>
            <input type="text" id="name" v-model="name">
            <br><br>
            <label for="email">Email:</label>
            <input type="email" id="email" v-model="email">
            <br><br>
            <button :disabled="!name || !email" type="submit">Submit</button>
        </form>
        <ul v-if="submissions.length > 0">
            <li v-for="(submission, index) in submissions" :key="index">
                <p>Name: {{ submission.name }}</p>
                <p>Email: {{ submission.email }}</p>
                <button @click="deleteSubmission(index)">Delete</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            email: '',
            submissions: []
        };
    },
    methods: {
        submitForm() {
            if (!this.name || !this.email) return
            const newSubmission = {
                name: this.name,
                email: this.email
            }
            this.submissions.push(newSubmission);
            this.name = '';
            this.email = '';
        },
        deleteSubmission(index) {
            this.submissions.splice(index, 1);
        },
        showMessage() {
            alert("Hello world!");
        }
    },
    computed: {
        message() {
            const count = this.submissions.length;
            if (count === 0) {
                return 'No Submissions Yet!';
            } else if (count === 1) {
                return '1 Submission';
            } else {
                return `${count} Submissions`
            }
        }
    }
}
</script>

<style>
form {
    font-family: 'Courier New', Courier, monospace;
}

h2 {
    font-family: 'Courier New', Courier, monospace;
    background-color: bisque;
}

button {
    font-family: 'Courier New', Courier, monospace;
    background-color: bisque;
}
</style>