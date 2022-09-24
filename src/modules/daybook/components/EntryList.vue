<template>
  <div class="entry-list-container">
      <div class="px-2 pt-2">
          <input 
            type="text"
            class="form-control"
            placeholder="Search"
            >
      </div>
      <div class="entry-scrollarea mt-3">
          <h2
            v-for="item in 100"
            :key=item
          >
            <Entry/>
          </h2>
      </div>
  </div>
</template>

<script>
import { defineAsyncComponent } from '@vue/runtime-core'
export default {
  components: {
      Entry: defineAsyncComponent(()=> import("../components/EntryComponent.vue"))
  }

}
</script>

<style lang="scss" scoped>
  .entry-list-container {
    border-right:1px solid  #252525;
    height: calc(100vh - 56px);
  }
  .entry-scrollarea {
    height: calc(100% - 80px);
    overflow-y: scroll;
    &::-webkit-scrollbar {
      width: 8px;
    }
    &::-webkit-scrollbar-thumb {
      border-radius: 10px;
      transition: 0s ease all;
      background: rgb(187, 187, 187);
    }
  }

</style>