<template>
  <div class="character">
      <img :src="character.image" :alt="character.name">
      <div class="character__info">
          <h3>{{character.name}}</h3>    
          <div class="status">
              <span
                  :class="
                    character.status == 'Alive' ?  'alive' : 
                    character.status == 'Dead' ? 'dead' : 
                    'default'
                   "
              ></span>
          </div>
          <div class="species">
              <span>
                  <strong>Species:</strong> {{character.species}}
              </span>
          </div>
          <div class="origin">
              <span>
                  <strong>Origin:</strong> {{character.origin.name}}
              </span>
          </div>
          <div class="location">
              <span>
                  <strong>Location:</strong>  {{character.location.name}}
              </span>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    props: ['character']
}
</script>

<style>
    .characters {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 3rem;
        margin: 3rem 0;
    }
</style>