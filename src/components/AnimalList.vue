<template>
  <div>
    <h1>List of animals</h1>

    <div class="container">
      <InputForm @add-animal="addNewAnimal" />
    </div>

    <table class="table">
      <tr>
        <th>Species</th>
        <th>Name</th>
        <th>Date of Birth</th>
      </tr>
      <tr v-for="(animal, index) in animals" :key="index">
        <td>{{animal.species}}</td>
        <td>{{animal.name}}</td>
        <td v-if="animal.dob === ''">Unknown</td>
        <td v-else>{{animal.dob}}</td>
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

    <!-- <template>
      <div>
        <b-table striped hover :items="animals">
          <template v-slot:cell(dob)="data">
            {{data.value ? data.value : 'Unknown'}}
          </template>
          <template v-slot:row-details="row">
            <b-button variant="danger">test</b-button>
          </template>
        </b-table>
      </div>
    </template> -->

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
          dob: '2010-02-12'
        },
        {
          species: 'Tiger',
          name: 'Shere Khan',
          dob: '2008-12-25'
        },
        {
          species: 'Panther',
          name: 'Bagheera',
          dob: '2015-06-02'
        },
        {
          species: 'Elephant',
          name: 'Dumbo',
          dob: '2001-08-10'
        },
        {
          species: 'Bear',
          name: 'Baloo',
          dob: ''
        },
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
      console.log('kiswbdvfuesw')
      this.animals.push(animal);
    }
  }
}
</script>