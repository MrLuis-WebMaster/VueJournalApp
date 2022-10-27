<template>
  <div class="entry-list-container">
      <div class="px-2 pt-2">
          <input 
            type="text"
            class="form-control"
            placeholder="Search"
            v-model="term"
            >
      </div>
      <div class="entry-scrollarea mt-3">
        <Entry
          v-for="entry in entriesByTerm"
          :key="entry.id"
          :entry="entry"
        />
      </div>
  </div>
</template>

<script>
import { defineAsyncComponent } from '@vue/runtime-core'
import { mapGetters } from 'vuex'
export default {
  components: {
      Entry: defineAsyncComponent(()=> import("../components/EntryComponent.vue"))
  },
  computed: {
    ...mapGetters('journal', ['getEntriesByTerm']),
    entriesByTerm() {
      return this.getEntriesByTerm(this.term)
    }
    
  },
  data(){
    return {
      term:''
    }
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