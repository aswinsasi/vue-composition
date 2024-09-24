<template>

    <h3>Name is change after 5sec (using reactive ref)- {{ name }}</h3>
</template>

<script>

import { ref } from 'vue'

export default {
name: 'DemoTwoComponent',

setup() {
    const name = ref('DemoTwoComponent');

    setTimeout(() => {
        name.value = 'aswin demo';
        console.log(name);
        
    },5000);

    return {
        name
    }
}
}
</script>