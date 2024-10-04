<template>

    <h3>Child component A</h3>
    <ChildB/>
</template>

<script>


import ChildB from './ChildB.vue';


export default {
name: 'ChildAComponent',

    components : {
        ChildB
    }
}


</script>