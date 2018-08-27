<template>
  <div id="edit-employee">
        <h3>edit</h3>
      <div class="row">
        <form @submit.prevent="updateEmployee" class="col s12">
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="employee_id">
   
  </div>
</div>
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="name">
   
  </div>
</div>
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="dept">
    
  </div>
</div>
<div class="row">
  <div class="input-field col s12">
    <input type="text" v-model="position">
    
  </div>
</div>
<button type="submit" class="btn">sub</button>
<router-link to="/">back</router-link>
        </form>
      </div>
  </div>
</template>

<script>
import db from './firebaseInit'
export default {
  name: 'edit-employee',
  data (){
      return{
employee_id:null,
          name: null,
          position: null,
          dept: null
      }
  },  
  beforeRouteEnter: (to, from, next) => {
    db.collection('employes')
    .where('employe_id', '==', to.params.employee_id)
    .get().then(querySnapshot => {
      querySnapshot.forEach(
        doc => {
          next(vm =>{
            vm.employee_id = doc.data().employe_id,
            vm.name = doc.data().name,
            vm.dept = doc.data().dept,
            vm.position = doc.data().position
          })
        }
      )
    })
  },
  watch:{
    '$route': 'fetchData'
  },
  methods:{
    fetchData(){
      db.collection('employes').where(
        'employe_id', '==', this.$route.params.employee_id
      ).get()
      .then(querySnapshot => {
        querySnapshot.forEach(
          doc => {
            this.employee_id = doc.data().employe_id,
            this.name = doc.data().name,
            this.dept = doc.data().dept,
            this.position = doc.data().position 
          }
        )
      })
    },
    updateEmployee(){
db.collection('employes').where(
        'employe_id', '==', this.$route.params.employee_id
      ).get()
      .then(querySnapshot => {
        querySnapshot.forEach(
          doc => {
           doc.ref.update({
             employe_id: this.employee_id,
             name: this.name,
             dept: this.dept,
             position: this.position
           })
           .then(() => {
             this.$router.push({name: 'view-employee', params: {employe_id: this.employee_id}})
           }) 
          }
        )
      })
  }
}}
</script>