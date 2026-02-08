<template lang="pug">
.accordion
  FaqAccordionItem(
    v-for="(item, index) in questionsAndAnswers"
    :key="index"
    v-bind="item"
    :id="index"
    :active="index === activeItem"
    @accordionSelect="accordionSelect"
  )
</template>

<script>
import FaqAccordionItem from '@/components/Landing/FaqAccordionItem.vue'

export default {
  components: { FaqAccordionItem },
  props: {
    questionsAndAnswers: Array
  },
  data () {
    return {
      activeItem: 0
    }
  },
  methods: {
    accordionSelect (id) {
      if (id === this.activeItem) {
        this.activeItem = -1
        return
      }
      this.activeItem = id
    }
  }
}
</script>

<style lang="scss" scoped>
.accordion {
  display: grid;
  grid-template-columns: minmax(0, 1fr);
  grid-gap: 1.6rem;
}
</style>
