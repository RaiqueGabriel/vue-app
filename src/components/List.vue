<template>
    <div class="list-form">
      <div>
        <h1>Lista de Livros</h1>
      </div>
      <div>
        <ul class="list-group">
          <li>Titulo: {{ livro.titulo }}, Editora {{ livro.editora }}, Paginas: {{ livro.paginas }} </li>
        </ul>
      </div>
    </div>
</template>

<script>
export default {
    props: {
        livro:{type: Object, required:true}
    }
}
</script>