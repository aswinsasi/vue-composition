<template>

    <h3>Child component B</h3>
    <ChildC/>
</template>

<script>


import ChildC from './ChildC.vue';


export default {
name: 'ChildBComponent',

    components : {
        ChildC
    }
}


</script>