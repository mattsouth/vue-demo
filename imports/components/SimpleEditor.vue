<template>
  <textarea class="form-control" v-on:keyup="$emit('keyup', $event)">{{text}}</textarea>
</template>

<script>
export default {
  props:['text']
}
</script>
