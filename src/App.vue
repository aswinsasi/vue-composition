<template>
 <DataComponent/>
 <DemoOne/>
 <DemoTwo/>
 <DemoThreeToRef/>
 <Method/>
 <VModel/>
</template>

<script>
import DataComponent from './components/Data.vue';
import DemoOne from './components/DemoOne.vue';
import DemoThreeToRef from './components/DemoThreeToRef.vue';
import DemoTwo from './components/DemoTwo.vue';
import Method from './components/Method.vue';
import VModel from './components/VModel.vue';

export default {
  name: 'App',
  components: {
    DataComponent,
    DemoOne,
    DemoTwo,
    DemoThreeToRef,
    Method,
    VModel
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
