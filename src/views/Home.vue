<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div>
      <div style="width: 50%">
      <ExampleInputText val="Hello"></ExampleInputText>
      <ExampleInputText :val="theValue"></ExampleInputText>
      </div>
      <div style="width: 50%">
      <ExampleSelectBox @custom-change="mychange"/>
      </div>
    </div>

    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import ExampleSelectBox from '../components/ExampleSelectBox';
import ExampleInputText from '../components/ExampleInputText';

export default {
  name: "Home",
  components: {
    HelloWorld,
    ExampleSelectBox,
    ExampleInputText
  },
  data() {
    return {
      theValue: null,
    }
  },
  methods: {
    mychange(val) {
      console.log('i got changed', val)
      this.theValue = val;
    }
  }
};
</script>
