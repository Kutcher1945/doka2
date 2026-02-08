<template lang="pug">
.accordion-item
  button.accordion-item__header(
    @click.prevent="$emit('accordionSelect', id)"
  ) {{ title }}
  .accordion-item__body(v-show="active") {{ text }}
</template>

<script>
export default {
  props: {
    id: Number,
    active: Boolean,
    title: String,
    text: String
  }
}
</script>

<style lang="scss" scoped>

.accordion-item {
  background: rgba(217, 217, 217, 0.12);
}
.accordion-item__header {
  display: block;
  cursor: pointer;
  width: 100%;
  text-align: left;
  outline: none;
  border: none;

  font-size: 2.3rem;
  line-height: 121%;
  color: #FFFFFF;
  padding: .8rem 1.2rem;
}
.accordion-item__body {
  font-size: 2rem;
  line-height: 121%;
  color: #FFFFFF;

  padding: 1.2rem;
}
</style>
