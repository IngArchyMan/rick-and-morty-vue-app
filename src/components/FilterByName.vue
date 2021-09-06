<template>
  <div class="search">
      <input type="text" placeholder="Search By Name" @keyup="filter()" v-model="name">
  </div>
</template>

<script>
import {ref} from 'vue'
import {useStore} from 'vuex'

export default {
    setup(){
        const store = useStore()
        const name = ref('')

        const filter = (()=>{
            store.dispatch('FilterByName', name.value)
        })

        return {
            name,
            filter
        }
    }

}
</script>

<style>
.search{
    width: 400px;
    margin: 3rem auto 0;
}

.search input{
    width: 400px;
    border: 1px solid var(--text-gray);
    background-color: transparent;
    border-radius: 10px;
    padding: 0.5rem;
    color: var(--text-white);
}

</style>