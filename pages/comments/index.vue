<template>
    <div class="main">
        <div class="container">
            <CHeading>Comments Index</CHeading>
    
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
    // page properties go here
}
</script>

<style>
.main {
    display: flex;
    justify-content: center;
    align-items: center;
}
.container {
    width: 50vw;
    height: 50vw;
    box-shadow: 0 10 20 10 #3333;
}
</style>