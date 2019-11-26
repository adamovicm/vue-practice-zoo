<template>
  <div>
    <h1>List of animals</h1>

    <div class="container">
      <InputForm @add-animal="addNewAnimal" :sectors="sectors" />
    </div>

    <table class="table">
      <tr>
        <th>Species</th>
        <th>Name</th>
        <th>Date of Birth</th>
        <th>Sector</th>
      </tr>
      <tr v-for="(animal, index) in animals" :key="index">
        <td>{{animal.species}}</td>
        <td>{{animal.name}}</td>
        <td v-if="animal.dob === ''">Unknown</td>
        <td v-else>{{animal.dob}}</td>
        <td>{{sectors[animal.sector]}}</td>
        <td>
          <b-button 
            variant="danger"
            @click="removeAnimal(index)"
            >
              Remove
          </b-button>
        </td>
        <td>
          <b-button 
            variant="outline-primary"
            @click="moveToTop(index)"
            >
              Move to top
          </b-button>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import InputForm from '@/components/InputForm.vue'
export default {
  components: {
    InputForm
  },
  data() {
    return {
      animals: [
        {
          species: 'Lion',
          name: 'Simba',
          dob: '2010-02-12',
          sector: 4
        },
        {
          species: 'Tiger',
          name: 'Shere Khan',
          dob: '2008-12-25',
          sector: 5
        },
        {
          species: 'Panther',
          name: 'Bagheera',
          dob: '2015-06-02',
          sector: 5
        },
        {
          species: 'Elephant',
          name: 'Dumbo',
          dob: '2001-08-10',
          sector: 4
        },
        {
          species: 'Bear',
          name: 'Baloo',
          dob: '',
          sector: 6
        },
      ],
      sectors: [
        'none',
        'Marine',
        'River',
        'Pond',
        'Savannah',
        'Jungle',
        'Tundra',
        'Avian',
        'Swamp'
      ]
    }
  },
  methods: {
    removeAnimal(index) {
      this.animals.splice(index, 1);
    },
    moveToTop(index) {
      // let tempAnimal = this.animal[index];
      // this.removeAnimal(index);
      // this.animals.unshift(tempAnimal);

      let newAnimals = this.animals.filter((item, i) => {
        item;
        return i != index;
      });

      newAnimals.unshift(this.animals[index]);
      this.animals = newAnimals
    },
    addNewAnimal(animal) {
      this.animals.push(animal);
    }
  }
}
</script>