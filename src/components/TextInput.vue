<template>
  <div>
      <label>{{name}}<input type="number" v-model="value" @change="onChange" /></label>
  </div>
</template>

<script>
export default {
    props: {
        name: String,
        startValue: {
            type: Number,
            default: 0
        }
    },
    data () {
        return {
            value: this.startValue
        }
    },
    methods: {
        onChange(){
            this.$emit('value-change', { name: this.name, value: Number(this.value) });
        }
    }
}
</script>

<style>

</style>