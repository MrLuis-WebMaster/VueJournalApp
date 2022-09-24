<template>
  <div class="entry-container mb-3 p-2 pointer"
    @click="$router.push({name:'entry', params:{id:10}})"
  >
      <div class="entry-tittle d-flex">
            <span class="text-primary fw-bold">15</span>
            <span class="mx-1">Mes</span>
            <span class="mx-2 fw-light fs-5">2022</span>
      </div>
      <div class="entry-description">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima sit asperiores, voluptate voluptates veritatis repudiandae quibusdam minus et libero impedit ullam optio repellendus iure commodi id sed quia, numquam cum vero labore facilis. Nobis sapiente nostrum, eum, perferendis sint repellat ad molestiae officiis cumque voluptatum nisi doloremque harum. Quis delectus at labore, quibusdam voluptas ut debitis! Saepe excepturi quas amet earum dolore reprehenderit corrupti vero recusandae exercitationem totam, consectetur debitis quod cupiditate incidunt iure. Qui id enim delectus dolores sapiente, ipsa ad nesciunt placeat commodi culpa doloribus soluta optio deserunt praesentium maiores cumque sed labore, nostrum mollitia aut sunt consequuntur.

      </div>
  </div>
</template>

<script>
export default {

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