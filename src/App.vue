<template>
  <div id="app">
    <ul>
      <li v-for="(value, key, index) in points" :key="index">
        <TextInput 
          :name="key"
          :start-value="value"
          @value-change="onValueChange"
        />
      </li>
    </ul>
    <DotPostioner
      :x="points.x" 
      :y="points.y" 
      :radius="points.radius"
    />
  </div>
</template>

<script>
import TextInput from './components/TextInput.vue';
import DotPostioner from './components/DotPositioner.vue';
export default {
  name: 'App',
  components: {
    TextInput,
    DotPostioner
  },
  data() {
    return {
      points: {
        x: 0,
        y: 0,
        radius: 3
      }
    }
  },
  methods:{
    onValueChange(e){
      this.points[e.name] = e.value;
      console.log(this.points);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
