<template>
  <div>
    <h1>List of animals</h1>

    <template>
      <div>
        <b-table striped hover :items="animals">
          
        </b-table>
      </div>
    </template>

  </div>
</template>

<script>
export default {
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
          dob: '2010-02-12'
        },
      ]
    }
  } 
  
    
}
</script>