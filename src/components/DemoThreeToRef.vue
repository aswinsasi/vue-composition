<template>
    <!-- without to ref it will not change -->
    <!-- <h3>{{ state.firstName }} {{ state.lastName }}</h3> -->

    <!-- normal data return -->
     <h4> {{ fName }} {{  lName }}</h4>

     <!-- if we use state.firstName without state it not reactive -->
      <h4> {{ firstName }} {{ lastName }}</h4>
</template>

<script>

import { reactive, toRefs } from 'vue'

export default {
name: 'DemoThreeComponent',

setup() {
   
    const state = reactive({
        firstName: 'aswin',
        lastName: 'sasi'
    });

    setTimeout(() => {
        state.firstName = 'aswin demo';
        state.lastName = 'sasi demo';
    //  console.log(firstName, lastName);

    },5000);

    // return {
    //     state,
    //     firstName: state.firstName,
    //     lastName: state.lastName
    // }

    return toRefs(state);
},
data() {
    return {
        fName: 'Swin',
        lName: 'sasi'
    }
}
}
</script>