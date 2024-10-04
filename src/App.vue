<template>
 <DataComponent/>
 <DemoOne/>
 <DemoTwo/>
 <DemoThreeToRef/>
 <Method/>
 <VModel/>
 <Computed/>
 <Watch/>
 <ProvideInject/>
</template>

<script>
import Computed from './components/Computed.vue';
import DataComponent from './components/Data.vue';
import DemoOne from './components/DemoOne.vue';
import DemoThreeToRef from './components/DemoThreeToRef.vue';
import DemoTwo from './components/DemoTwo.vue';
import Method from './components/Method.vue';
import ProvideInject from './components/ProvideInject.vue';
import VModel from './components/VModel.vue';
import Watch from './components/Watch.vue';

export default {
  name: 'App',
  components: {
    DataComponent,
    DemoOne,
    DemoTwo,
    DemoThreeToRef,
    Method,
    VModel,
    Computed,
    Watch,
    ProvideInject
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
