
<script>
export default {
    data() {
        return {
            name: 'theresa newman',
            status: 'active',
            tasks: [
                'task 1',
                'task 2',
                'task 3'
            ],
            link: 'https://www.google.com'
        }
    },
    methods: {
        toggleStatus() {
            if ( this.status === 'active' ) {
                this.status = 'pending'
            } else if ( this.status === 'pending' ) {
                this.status = 'inactive'
            } else {
                this.status = 'active'
            }
        }
    }
}
</script>
<template>
<h1>{{ name }}</h1>
    <p v-if="status === 'active'">
        User Is Active
    </p>
    <p v-else-if="status === 'pending'">
        User is Pending
    </p>
    <p v-else>User is Inactive</p>
    <h3>Tasks</h3>
    <ul>
        <li v-for="task in tasks" :key="task">{{ task }}</li>
    </ul>
<!--    <a v-bind:href="link">go to google</a>-->
    <a :href="link">go to google</a>

<!--    <button v-on:click="toggleStatus">Change status</button>-->
    <button @click="toggleStatus">Change status</button>
</template>
