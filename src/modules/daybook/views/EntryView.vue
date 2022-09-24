import { defineAsyncComponent } from '@vue/runtime-core';
<template>
  <div class="entry-tittle d-flex justify-content-between p-2">
    <div>
        <span class="text-primary fs-5 fw-bold">15</span>
        <span class="mx-1">Julio</span>
        <span>2022</span>
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
    <textarea class="form-control" placeholder="Que sucedio hoy?"></textarea>
  </div>
  <img class="img-fluid img-thumbnail" src="https://www.tooltyp.com/wp-content/uploads/2014/10/1900x920-8-beneficios-de-usar-imagenes-en-nuestros-sitios-web.jpg" alt="alt">
  <Fab/>
</template>

<script>
import {defineAsyncComponent} from 'vue'
export default {
    components: {
        Fab: defineAsyncComponent(()=> import('../components/FabAction.vue'))
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