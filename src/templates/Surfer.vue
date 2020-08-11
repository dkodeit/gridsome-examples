<template>
  <layout>

    <div class="images">
      
      <div>
      
        <g-image 
          :src="$page.surfer.src" 
          :alt="$page.surfer.alt" />
        
      </div>

    </div>

  </layout>
</template>

<page-query>
query Surfer($id: ID) {
  surfer(id: $id) {
    id
    src(width: 800, quality: 90)
    alt
  }
}
</page-query>

<style scoped>
.images img {
  max-width: 100%;
  height: auto;
}
</style>
