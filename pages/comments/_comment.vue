<template>
    <div class="main">
        <div class="container">
            <CHeading>Comment - method like NS App, has index.vue</CHeading>
            <p>Name</p>
            <p>{{ comment.name }}</p>
            <br>
            <p>Email</p>
            <p>{{ comment.email }}</p>
            <br>
            <p>Body</p>
            <p>{{ comment.body }}</p>
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
            comment: {
                name: 'loading',
                email: 'loading',
                body: 'loading',
            }
        }
    },
    async created() {
        await this.getComment()
    },
    methods: {
        async getComment() {
            const { comment } = this.$route.params

            const res = await fetch(`https://jsonplaceholder.typicode.com/comments/${comment}`)
            const data = await res.json()
            this.comment = data
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