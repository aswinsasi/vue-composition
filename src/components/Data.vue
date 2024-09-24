<template>
    <!-- for single ref is gud in place of use reactive bcs reactive is object -->
     <input type="text" ref="head">
     <h2> Optional firstname - {{ o_firstname }}</h2>
     <h2> Composition firstname - {{ c_firstname }}</h2>
    <h2> Composition greet - {{ greet }}</h2>

    <!-- reactive -->
     <h2>optional firstname - {{ o_firstname }}</h2>
     <h2>optional lastname - {{ o_lastname }}</h2>
     <h2>optional heroname - {{ o_heroname }}</h2>

     <h2>composition firstname - {{ c_firstname }}</h2>
     <h2>Composition lastname - {{ c_lastname }}</h2>
     <h2>Composition heroname - {{ c_heroname }}</h2>
     <h2>Composition greet - {{ greetHero }}</h2>
     <h3> {{  state.firstname }}</h3>
     <h4> test - {{ test }}</h4>
      
</template>

<script>

import { reactive, ref } from 'vue';

export default {
name: 'DataComponent',

mounted() {
    console.log(this.$refs.head.focus())
},

//composition firstname
setup() {
    const c_firstname = ref('Aswin sasi');
    const test = ref('Test syntax');
    c_firstname.value = 'Diana';
    const greet = `hai ${c_firstname.value}`;
    console.log(c_firstname);

    const c_lastname = ref('sasi');
    const c_heroname = ref('batman');

    const greetHero = `hello ${c_firstname.value} is ${c_lastname.value} and ${c_heroname.value}`;

    const isLogedIn = ref(false);

    const IsLogin = reactive({
        value: false
    });

    const state = reactive({
        firstname: 'aswin',
        lastname: 'sasi',
        heroname: 'womdermen'
    });

    return {
        c_firstname,
        greet,
        greetHero, 
        state,
        test,
        isLogedIn,
        IsLogin
    }
},

//optional firstname
data() {
    return {
        o_firstname: 'sunu',
        o_lastname: 'sahadevan',
        o_heroname: 'superman',
    }
}
}
</script>

<style scoped>
</style>