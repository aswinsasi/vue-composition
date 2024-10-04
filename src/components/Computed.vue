<template>
<br>
<h2>Computed </h2>
   <!-- computed with option -->
    <input type="text" placeholder="first name" v-model="fname">
    <input type="text" placeholder="last name" v-model="lname">

    <h4>Optional full name - {{ fullName }}</h4>

    <input type="text" placeholder="first name" v-model="refFirstName">
    <input type="text" placeholder="last name" v-model="refLastName">

    <h4>composition full name with ref- {{ refFullName }}</h4>

    <input type="text" placeholder="first name" v-model="reactiveFirstName">
    <input type="text" placeholder="last name" v-model="reactiveLastName">

    <h4>composition full name with reactive- {{ reactiveFullName }}</h4>



</template>

<script>

import { ref, computed, reactive, toRefs } from 'vue';

export default {
name: 'ComputedComponent',


setup () {
    const refFirstName = ref('')
    const refLastName = ref('');

    const refFullName = computed( function () {
        return refFirstName.value + ' ' + refLastName.value;
    });

    const state = reactive({
        reactiveFirstName: '',
        reactiveLastName: '',
    });

    const reactiveFullName = computed( function () {
        return `${state.reactiveFirstName} ${state.reactiveLastName}`
    });

    return {
        refFirstName,
        refLastName,
        refFullName,
        ...toRefs(state),
        reactiveFullName
    }
},

computed: {
    fullName() {
        return this.fname + ' ' + this.lname
    }
},
data() {
    return {
        fname: '',
        lname: '',
    }
}
}
</script>