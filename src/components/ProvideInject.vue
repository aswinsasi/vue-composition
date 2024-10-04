<template>

    <h3>Parent component name -  {{ name }}</h3>
    <ChildA/>
    <h3>Parent component count -  {{ count }}</h3>
    <h3>Parent component firstName -  {{ firstName }}</h3>
    <h3>Parent component lastName -  {{ lastName }}</h3>
    <button @click="incrementCount">Increment Parent</button>

</template>

<script>


import { provide, reactive, ref, toRefs } from 'vue';
import ChildA from './ChildA.vue';

export default {
name: 'ProvideInjectComponent',

setup() {

    const heroName = ref('BatMan');
    const count = ref(0);

    const state = reactive({
        firstName: 'Aswin',
        lastName: 'Sasi'
    });

    function incrementCount() {
        count.value++;
    }
    
    provide('c_heroName', heroName);
    provide('c_count', count);
    provide('c_state', state);
    provide('c_incrementCount', incrementCount);

    return {
        count,
        ...toRefs(state),
        incrementCount
    }


},
data() {
    return {
        name: 'aswin',
    }
},
provide(){
    return {
        username: this.name
    }
},
components: {
    ChildA
}
}


</script>