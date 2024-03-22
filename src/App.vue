<script setup>
import { onMounted, ref } from 'vue';
import Card from './components/Card.vue';

  //variavel que deve ser relacionada com o input
  const pesquisa = ref("")
  //variavel que vai receber o(s) pokemon(s) da API
  const pokemons = ref([1])

  function getPokemons() {
    //faça a função para buscar os 8 pokemons iniciais aqui
  
    // para limitar a 8 pokemons, faça a requisição assim: .get("/pokemon?limit=8")
  
    //a pesquisa deve inserir os pokemons dentro da variavel 'pokemons'
  }

  onMounted(getPokemons)

  function handleSubmit() {
    //aqui faça a função para buscar o pokemon que foi digitado no input
    //o pokemon encontrado deve ser novo valor da variavel 'pokemons'
  }

</script>

<template>
  <section className="container">
    <img id='APIlogo' src="/pokeapi_logo.png" alt="PokeAPI" />
    <form>
      <input
        type="text"
        placeholder="Pesquisar"
      />
      <button type="submit" onClick={handleSubmit}>
        Pesquisar
      </button>
    </form>

    <section className="grid">
        <Card
          v-for="(pokemon, index) in pokemons"
          :key={index}
          :name="pokemon?.name || 'Nome do Pokemon'"
          :image="pokemon?.sprites?.other?.dream_world?.front_default"
        />
    </section>
  </section>

</template>

<style scoped>
.container {
  display: flex;
  width: 100%;
  flex-direction: column;
}

#APIlogo {
  align-self: center;
  margin-top: 2rem;
  width: 20%;
}

form {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 3.2rem;
}

input {
  width: 100%;
  height: 40px;
  border-radius: 10px 0 0px 10px;
  background: #f1f1f1;
  border: 1px solid #f1f1f1;
  padding-left: 10px;
}

input:hover {
  border: 1px solid rgb(212, 210, 210);
  transition: 0.2s ease-in-out;
}

button {
  border-radius: 0 10px 10px 0px;
  background: #3761a8;
  color: white;
  height: 45px;
  border: 1px solid;
  cursor: pointer;
  padding: 10px;

  color: #fff;
  font-family: "Inter", sans-serif;
  font-size: 1rem;
  font-weight: 600;
}

button:hover {
  background-color: #3c6ab9;
  transition: 0.2s ease-in-out;
}

.grid {
  display: grid;
  align-self: center;

  grid-template-columns: repeat(1, 1fr);

  gap: 40px;
}

@media (min-width: 768px) {
  input {
    width: 33%;
  }
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>

