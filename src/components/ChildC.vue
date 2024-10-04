<template>

    <h3>Child component C</h3>
    <h3> Inject optional from Parent name - {{ username }}</h3>

    <h3> Inject composition from Parent hero name - {{ heroName }}</h3>
    <h3> Inject composition from Parent count - {{ count }}</h3>
    <h3> Inject composition from Parent first name - {{ firstName }}</h3>
    <h3> Inject composition from Parent last name - {{ lastName }}</h3>

    <button @click="incrementCount">Increment Child</button>
</template>

<script>
import { inject, toRefs } from 'vue';




export default {
name: 'ChildCComponent',

setup() {
    const heroName = inject('c_heroName', 'spiderName');
    const count = inject('c_count');
    const state = inject('c_state', {});
    const incrementCount = inject('c_incrementCount');
    return {
        heroName,
        count,
        ...toRefs(state),
        incrementCount
    }
},

inject: [
    'username'
]
   
}


</script>