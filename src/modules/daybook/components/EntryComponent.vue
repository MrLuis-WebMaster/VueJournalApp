<template>
  <div class="entry-container mb-3 p-2 pointer"
    @click="$router.push({name:'entry', params:{ id: entry.id }})"
  >
      <div class="entry-tittle d-flex">
            <span class="text-primary fw-bold">{{day}}</span>
            <span class="mx-1">{{month}}</span>
            <span class="mx-2 fw-light fs-5">{{yearDay}}</span>
      </div>
      <div class="entry-description">
        {{shortText}}
      </div>
  </div>
</template>

<script>
import getDayMonthYear from '../helpers/getDayMonthYear';
export default {
  props: {
    entry: {
      type: Object,
      required: true
    }
  },
  computed: {
    shortText() {
      return ( this.entry.text.length > 300) 
      ? this.entry.text.substring(0,300) + "..."
      : this.entry.text
    },
    day () {
      return getDayMonthYear(this.entry.date).day
    },
    month () {
      return getDayMonthYear(this.entry.date).month
    },
    yearDay () {
      return getDayMonthYear(this.entry.date).yearDay
    }
  }
}
</script>

<style lang="scss" scoped>
  .entry-container {
    border-bottom: 1px solid #f3f3f3;
    transition: .2s all ease-in;
    cursor: pointer;
    margin-left: 8px;
    &:hover {
      background-color: lighten($color: #7c7c7c, $amount: 45);
    }
    .entry-description {
      font-size: 12px;
      text-align: justify;
      padding: 8px;
    }
  }

</style>