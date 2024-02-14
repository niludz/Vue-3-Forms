<template>
  <label v-if="slabel">{{slabel}}</label>
  <select :value="modelValue" class="field"
    :="{...$attrs,
    onChange:($event)=>{$emit('Update:modelValue',$event.target.value)}}">
    <option
      v-for="option in options"
      :value="option"
      :key="option"
      :selected="option === modelValue"
    >{{ option }}</option>
  </select>
</template>
<script>
export default {
  props: {
    slabel: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    },
    options: {
      type: Array,
      required: true
    }
  }
}
</script>
