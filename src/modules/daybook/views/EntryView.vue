
<template>
  <div 
        v-if="entry"
        class="entry-tittle d-flex justify-content-between p-2">
    <div>
        <span class="text-primary fs-5 fw-bold">{{day}}</span>
        <span class="mx-1">{{month}}</span>
        <span>{{yearDay}}</span>
    </div>
    <div class="d-flex gap-2">
        <button class="btn btn-danger">
            Delete
        </button>
        <button class="btn btn-primary">
            Upload Image
        </button>
    </div>
  </div>
  <hr>
  <div class="d-flex flex-column px-3 h-75">
    <textarea class="form-control" placeholder="Que sucedio hoy?" v-model="entry.text"></textarea>
  </div>
  <img class="img-fluid img-thumbnail" src="https://www.tooltyp.com/wp-content/uploads/2014/10/1900x920-8-beneficios-de-usar-imagenes-en-nuestros-sitios-web.jpg" alt="alt">
  <Fab icon="fa-save"/>
</template>

<script>
import {defineAsyncComponent} from 'vue'
import { mapGetters } from 'vuex';
import getDayMonthYear from '../helpers/getDayMonthYear'
export default {
    props: {
        id: {
            type: String,
            required: true
        }
    },
    components: {
        Fab: defineAsyncComponent(()=> import('../components/FabAction.vue'))
    },

    data() {
        return {
            entry: null
        }
    },

    computed: {
        ...mapGetters('journal', ['getEntriesById']),
        day () {
            return getDayMonthYear(this.entry.date).day
        },
        month () {
            return getDayMonthYear(this.entry.date).month
        },
        yearDay () {
            return getDayMonthYear(this.entry.date).yearDay
        }
    },

    methods:{
        loadEntry() {
            const entry = this.getEntriesById( this.id )
            if (!entry) return this.$router.push({name: 'no-entry'})
            this.entry = entry
        }
    },
    created() {
        this.loadEntry()
    },
    watch: {
        id() {
            this.loadEntry()
        }
    }
}
</script>

<style lang="scss" scoped>
    textarea {
        font-size: 20px;
        border: none;
        height: 100%;
        &:focus {
            box-shadow: none;
            outline: none;
        }
    }
    img {
        width: 200px;
        position: fixed;
        bottom: 150px;
        right: 20px;
    }
</style>