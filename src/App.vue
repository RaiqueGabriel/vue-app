<template>
  <div id="app">
    <div class="container"> 
        <div class="tittle">
          <h1>Registro de Livros</h1>
        </div>
        <div class="register-form">
            <form class="needs-validation" @submit.prevent="addLivro(livro)">
                <div class="form-row">
                    <div class="col">
                        <label for="validationCustom03">Titulo</label>
                        <input type="text" class="form-control" v-model="livro.titulo" required>
                    </div>
                </div>
                <div class="form-row">
                    <div class="col">
                        <label for="validationCustom01">Editora </label>
                        <input type="text" class="form-control" v-model="livro.editora" required>
                    </div>
                    <div class="col">
                        <label for="validationCustom02">Paginas</label>
                        <input type="text" class="form-control" v-model="livro.paginas" required>
                    </div>
                </div>
                <button class="btn btn-primary" type="submit" id="submit-button">Salvar</button>
            </form>
        </div>
    </div>
    <List v-for="l in livros" :key="l.id" :livro="l"/>
  </div>
</template>

<script>
import List from './components/List';

export default {
  name: 'App',
  components:{ 
    List 
  },
  data() {
    return{
      livros: [],
      livro:{}
    }
  },
  methods:{
    addLivro(livro){
      livro.id = Date.now();
      this.livros.push(livro);
      this.livro = {}
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.selector-for-some-widget {
  box-sizing: content-box;
}

.register-form {
    margin:0 auto; 
    width:600px;
    padding:20px;
    background:#f9f9f9;
    border:2px solid #333;
}

.list-form {
    margin:0 auto; 
    width:600px;
    padding:20px;
    background:#f9f9f9;
    border:2px solid #333;
}

.container {
    margin-bottom: 2%;
}

#submit-button {
    margin-top: 2%;
}

ul {
    list-style-type: none;
}
</style>
