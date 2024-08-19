<template>
    <div class="main">
        <div class="container">
            <CHeading>User - method like NS app</CHeading>
            <p>Name</p>
            <p>{{ user.name }}</p>
            <br>
            <p>username</p>
            <p>{{ user.username }}</p>
            <br>
            <p>email</p>
            <p>{{ user.email }}</p>
        </div>
    </div>
</template>

<script>import {
    CHeading
} from '@chakra-ui/vue'

export default {
    components: {
        CHeading
    },
    data() {
        return {
            user:{
                name: 'loading',
                username: 'loading',
                email: 'loading',
            }
        }
    },
    async created() {
        await this.getUser()
    },
    methods: {
        async getUser() {
            const { user } = this.$route.params

            const res = await fetch(`https://jsonplaceholder.typicode.com/users/${user}`)
            const data = await res.json()
            this.user = data
        }
    }
}
</script>

<style>
.main {
    display: flex;
    justify-content: center;
    align-items: center;
}
.container {
    padding: 2rem;
    width: 50vw;
    height: 50vw;
    box-shadow: 0 10 20 10 #3333;
}
</style>