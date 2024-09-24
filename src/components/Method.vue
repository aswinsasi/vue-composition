<template>

    <h3>name is - {{  name }}</h3>
    <button @click.prevent="changeName">Change Name</button>

    <!-- replace method into composition ref-->
     <h4> count - {{ count }}</h4>
     <button @click.prevent="incrementCount">Change Count</button>

     <!-- replace method with composition reactive -->

      <h4> hero name - {{  fname }} {{ lname }}</h4>
      <button @click.prevent="changeHero(fname)">Change Hero</button>
</template>

<script>

import { reactive, ref, toRefs } from 'vue';

export default {
name: 'DemoOneComponent',

setup() {
     const count = ref(0);

    function incrementCount() {
        count.value = count.value + 1;
    }

    const state = reactive({
        fname: 'super',
        lname: 'man'
    });

    function changeHero(fname) {
        console.log(fname)
        state.fname = 'bat';
        state.lname = 'Man';
    }

    return {
        count,
        incrementCount,
        ...toRefs(state),
        changeHero
    }

},

data() {
    return {
        name: 'vishvas'
    }
},
methods: {
    changeName() {
        this.name = 'arjun jacob';
    }
}
}
</script>