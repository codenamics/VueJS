<template>
  <div id="view-employee">
    <ul class="collection with-header">
      <li class="collection-header">{{name}}</li>
      <li class="collection-item">{{employee_id}}</li>
       <li class="collection-item">{{dept}}</li>
        <li class="collection-item">{{position}}</li>
    </ul>
    <router-link to="/" class="btn grey">Back</router-link>
     <button @click="deleteEmployee" class="btn red">Delete</button>
  <div class="fixed-action-btn">
        <router-link v-bind:to="{name: 'edit-employee', params: {employee_id: employee_id}}" class="btn-floating yellow">
        <i class="fa fa-pencil"></i>
        </router-link>
      </div>
  </div>
  
</template>

<script>
import db from './firebaseInit'
export default {
  name: 'view-employee',
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
    deleteEmployee (){
      if(confirm('Are you sure??')){
      db.collection('employes').where('employe_id', '==', 
      this.$route.params.employee_id).get()
      .then(querySnapshot => {
        querySnapshot.forEach(
          doc => {
            doc.ref.delete();
            this.$router.push('/');
          }
        )
      })
      }
    }
  }
}
</script>