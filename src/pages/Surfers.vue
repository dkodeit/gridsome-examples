<template>
  <layout>

    <div class="images">
      
      <div v-for="{ node } in $page.allSurfer.edges" :key="node.id">
      
        <g-link :to="`/surfer/${node.id}/`">
          <g-image 
            :src="node.src" 
            :alt="node.alt" />
        </g-link>
        
      </div>

    </div>

  </layout>
</template>

<page-query>
query {
  allSurfer {
    edges {
      node {
        id
        # src // without options
        src(width: 250, height: 250, fit: cover, quality: 80)
        alt
      }
    }
  }
}
</page-query>

<style scoped>
.images {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px,1fr));
  gap: 1rem;
  justify-items: center;
}
.images img {
  max-width: 100%;
  height: auto;
  display: block;
}
</style>
