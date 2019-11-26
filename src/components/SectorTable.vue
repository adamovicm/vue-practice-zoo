<template>
  <div>
    <h3>List of Sectors</h3>

    <table class="table">
      <tr v-for="(sector, index) in sectors" :key="index">
        <td>{{ sector }}</td>
        <td>
          <button 
            class="btn btn-primary"
            @click.prevent="showAnimalList(index)"
          >List of Animals</button>
        </td>
      </tr>

    </table>
  </div>  
</template>

<script>
export default {
  props: [
    'sectors',
    'animals'
  ],
  methods: {
    showAnimalList(index) {
      let animalsInSector = [];
      
      this.animals.forEach(animal => {
        if (animal.sector === index) {
          animalsInSector.push(animal.name);
        }
      })

      if(animalsInSector.length == 0) {
        alert('No animals in this sector.');
      } else {
        alert('Animals in this sector: ' + animalsInSector);
      }
    }
  }
}
</script>
