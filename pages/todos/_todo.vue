<template>
    <div class="main">
        <div class="container">
            <CHeading>Todo - fetch() api</CHeading>
            <p>Title</p>
            <p>{{ todo.title }}</p>
            <br>
            <p>completed</p>
            <p>{{ todo.completed }}</p>
        </div>
    </div>
</template>

<script lang="js">
import {
   
    CHeading
} from '@chakra-ui/vue'

export default {
    components: {
       
        CHeading
    },
    // page properties go here
    data() {
        return {
            todo: {
                title: 'loading',
                completed: 'loading',
            }
        }
    },
    async fetch() {
        const { todo } = this.$route.params
        this.todo = await this.$http.$get(`https://jsonplaceholder.typicode.com/todos/${todo}`)
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