<script setup>

const { image, name } = defineProps({
  image: String,
  name: String,
});

</script>

<template>
  <section className="card">
    <img className='pokemonImg' :src="image || 'https://down-br.img.susercontent.com/file/c841c80c94c16341e5722c8f68644b8d'" :alt="name || 'Poke API'" />
    <div className='textSection'>
      <p className='title'>{{name}}</p>
      
       <!-- você pode escolher mais informações para serão exibidas aqui: -->
      <p className='description'></p>
      <p className='description'></p>
    </div>
  </section>
</template>

<style>
.card {
  width: 181px;
  display: flex;
  flex-direction: column;
  text-align: center;
  padding-bottom: 24px;
  border-radius: 10px;
  background: #fff;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  cursor: pointer;
}

.card:hover {
  transform: scale(1.1);
  transition: 0.5s;
}

img {
  width: 90%;
  align-self: center;
}

p {
  margin: 0;
}

.title {
  color: #3761a8;
  text-align: center;
  font-family: "Concert One", cursive;
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}

.description {
  color: #1e1e1e;
  text-align: center;
  font-family: "Poppins", sans-serif;
  font-size: 1.1rem;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}

.textSection {
  display: flex;
  flex-direction: column;
  gap: 5px;
}
</style>