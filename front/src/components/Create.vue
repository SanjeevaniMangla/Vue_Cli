<template>
  <div class="container mt-4">
    <form @submit.prevent="insertArticle">
        <input
        type="text"
        class="form-title"
        placeholder="Please enter your Title"
        v-model="title"
        style="width: 99.8%;">
        <br/>
        <br>

        <textarea rows="10"
        class="form-control"
        placeholder="Please enter the description"
        v-model="body"></textarea>

        <button class="btn btn-success mt-4">Publish Article</button>

        <div v-if="error"
        class="alert alert-warning alert-dismissible fade show mt-5"
        role="alert">
        <strong>{{ error }}</strong>
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
        </div>
        

    </form>
  </div>
</template>

<script>
export default {
    data(){
        return{
            title:null,
            body:null,
            error:null
        }
        
    },
    methods:{
        insertArticle(){
            if(!this.title || !this.body){
                this.error = "Please add all fields"
            }
            else{
                fetch('http://127.0.0.1:5000/add',{
                  method:"POST",
                  headers:{
                      'Content-Type':'application/json'
                  },
                  body: JSON.stringify({title:this.title, body:this.body})
              })
              .then(resp => resp.json())
              .then(() => {
                  this.$router.push({
                    name:'home'
                  })
              })
              .catch(error => {
                  console.log(error)
              })
            }
        }
    }

}
</script>

<style>

</style>