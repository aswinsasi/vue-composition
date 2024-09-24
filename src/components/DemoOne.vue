<template>

    <h3>Name is not change after 5sec (not using reactive ref)- {{ name }}</h3>
</template>

<script>

export default {
name: 'DemoOneComponent',

setup() {
    let name = 'DemoOneComponent';

    setTimeout(() => {
        name = 'aswin demo';
        console.log(name);
        
    },5000);

    return {
        name
    }
}
}
</script>