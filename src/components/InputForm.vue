<template>
  <div>
    <b-form inline>
      <label class="sr-only" for="inline-form-input-species">Species</label>
      <b-input
        id="inline-form-input-species"
        class="mb-2 mr-sm-2 mb-sm-0"
        placeholder="Species"
        v-model="animal.species"
      ></b-input>

      <label class="sr-only" for="inline-form-input-name">Name</label>
      <b-input
        id="inline-form-input-name"
        class="mb-2 mr-sm-2 mb-sm-0"
        placeholder="Name"
        v-model="animal.name"
      ></b-input>
      
      <label class="sr-only" for="inline-form-input-dob">dob</label>
      <b-input
        id="inline-form-input-dob"
        class="mb-2 mr-sm-2 mb-sm-0"
        placeholder="Date of birth"
        v-model="animal.dob"
      ></b-input>

      <b-button 
        variant="primary" 
        @click.prevent="addAnimal"
      >Add Animal</b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      animal: {
        species: '',
        name: '',
        dob: ''
      }
    }
  },
  props: [
    'animals'
    ],
  methods: {
    addAnimal() {
      this.$emit('add-animal', this.animal)
      
    }
  }
}
</script>