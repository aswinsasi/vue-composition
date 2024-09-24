<template>

    <h3>Check on vue on inspect to see v model change</h3>
<br>
    <input type="text" name="fname" placeholder="first name" v-model="fname">
    <input type="text" name="lname" placeholder="last name" v-model="lname">
<br>
    <!-- ref -->
    <input type="text" name="heroName" placeholder="hero name" v-model="heroName">
<br>
    <!-- reactive -->
    <input type="text" name="firstName" placeholder="first name" v-model="firstName">
    <input type="text" name="lastName" placeholder="first name" v-model="lastName">
</template>

<script>

import { ref, reactive, toRefs } from 'vue'

export default {
name: 'VModelComponent',

//composition
setup() {
    //ref
    const heroName = ref('');

    heroName.value = "arjun";

    const state = reactive({
        firstName: '',
        lastName: ''
    });

    return {
        heroName,
        ...toRefs(state),
    }
},

//optional
data() {
    return {
        fname: '',
        lname: ''
    }
}
}
</script>