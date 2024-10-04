<template>

    <h2>Watcher Composition (log check)</h2>
    <input type="text" placeholder="Enter your name" v-model="name" />
    <br>
    <input type="text" placeholder="Enter your name" v-model="firstName" />
    <br>
    <input type="text" placeholder="Enter your superhero" v-model="superHero" />
    <br>
    <input type="text" placeholder="Enter your firstName" v-model="fName" />
    <br>
    <input type="text" placeholder="Enter your lastName" v-model="lName" />
    <br>
    <input type="text" placeholder="Enter actor name" v-model="options.actorName" />
</template>

<script>


import { ref, watch, reactive, toRefs } from 'vue';
import _ from 'lodash';
export default {
  props: {
  },
name: 'WatchComponent',

setup() {

    const firstName = ref('');
    const superHero = ref('batman');

    //only one

    watch(firstName , (newValue, oldValue) => {
        console.log('composition new: ' + newValue);
        console.log('composition old: ' + oldValue);
    });

    //multiple
     watch([firstName, superHero] , (newValue, oldValue) => {
        //firstname consider as 0 th superhero consider as 1
        console.log('composition new superhero: ' + newValue[1]);
        console.log('composition old superhero: ' + oldValue[1]);

        console.log('composition new firstName: ' + newValue[0]);
        console.log('composition old firstName: ' + oldValue[0]);
    }, { immediate: true });

    //reactive

    const state = reactive({
        fName: '',
        lName: '',
        options: {
            actorName: ''
        }
    });

    watch(state, (newValue, oldValue)  =>{
        console.log('reactive fname old:', oldValue.fName)
        console.log('reactive lName old:', oldValue.lName);

        console.log('reactive fname old:', newValue.fName)
        console.log('reactive lName old:', newValue.lName);
    });

    watch(()=> { return {...state} }, (newValue, oldValue)  =>{
        console.log('reactive fname old:', oldValue.fName)
        console.log('reactive lName old:', oldValue.lName);

        console.log('reactive fname old:', newValue.fName)
        console.log('reactive lName old:', newValue.lName);
    });


    watch(() => state.fName, (newValue, oldValue) => {
        console.log('reactive individual watch  new fname', newValue)
        console.log('reactive individual watch  old fname', oldValue)
    });


    watch(() => _.cloneDeep(state.options), (newValue, oldValue) => {
        console.log('reactive individual watch  new options', newValue.actorName)
        console.log('reactive individual watch  old options', oldValue.actorName)
    }, { deep: true });

    

    return {
        firstName,
        superHero,
        ...toRefs(state),
    }

},


watch : {

    name: {
        handler(newValue, oldValue) {
            console.log('optional old: '+oldValue);
            console.log('optional new: '+newValue);
        },
        immediate: true
    }

},

data() {
    return {
        name: 'asw'
    }
}
}
</script>