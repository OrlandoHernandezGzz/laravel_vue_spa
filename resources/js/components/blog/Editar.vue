<template>
  <div class="container">
      <div class="row">
          <div class="col-12">
              <div class="card-header">
                  <h4>Crear Blog</h4>
              </div>
              <div class="card-body">
                  <form @submit.prevent="actualizar">
                      <div class="row">
                          <div class="col-12 mb-2">
                              <div class="form-group">
                                  <label for="">Titulo</label>
                                  <input type="text" class="form-control" v-model="blog.titulo">
                              </div>
                          </div>
                          <div class="col-12 mb-2">
                              <div class="form-group">
                                  <label for="">Contenido</label>
                                  <textarea class="form-control" v-model="blog.contenido" cols="30" rows="10"></textarea>
                              </div>
                          </div>
                          <div class="col-12">
                              <div class="form-group">
                                  <button type="submit" class="btn btn-warning">Actualizar</button>
                              </div>
                          </div>
                      </div>
                  </form>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "editar-blog",
    data(){
        return{
            blog:{
                titulo:"",
                contenido:""
            }
        }
    },
    mounted(){
        this.mostrarBlog()
    },
    methods:{
        async mostrarBlog(){
            this.axios.get(`/api/blog/${this.$route.params.id}`)
            .then(response=>{
                const {titulo, contenido} = response.data
                this.blog.titulo = titulo
                this.blog.contenido = contenido
            })
            .catch(error=>{
                console.log(error)
            })
        },
        async actualizar(){
            this.axios.put(`/api/blog/${this.$route.params.id}`, this.blog)
            .then(response=>{
                this.$router.push({
                    name:"mostrarBlog"
                })
            })
            .catch(error=>{
                console.log(error)
            })
        }
    }
}
</script>

<style>

</style>