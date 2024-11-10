<script setup>

import linkedin from '/src/assets/icons8-linkedin.gif';
import instagram from '/src/assets/icons8-instagram-viejo.gif';
import github from '/src/assets/icons8-github.gif';
import cv from '/src/assets/icons8-curriculum-vitae-50.png';

const title = 'Omar Ignacio Velazquez';
const descripcion = 'Técnico Universitario en Programación - UTN';
const residencia = 'Jachal, San Juan, Argentina';
const presentacion = 'Hola, soy Nacho👋FullStack Developer Soy desarrollador FullStack MERN con año y medio de experiencia en la creación de aplicaciones web';
const redesSociales = [
  { id: 1, name: 'linkedin', src: linkedin, url: 'https://www.linkedin.com/in/omar-ignacio-velazquez-44499414a/' },
  { id: 2, name: 'Instagram', src: instagram, url: 'https://github.com/IgnacioVelazquez92' },
  { id: 3, name: 'github', src: github, url: 'https://github.com/IgnacioVelazquez92' },
  { id: 4, name: 'curriculum', src: cv, url: '/src/assets/CV_VELAZQUEZ_2024.pdf' },
];
const telefono = '+54 9 381-4443608';

</script>

<template>
    <section class="datos-personales">
        <div class="card">
            <h1>{{ title }}</h1>
            <h2>{{ descripcion }}</h2>
            <p>{{ presentacion }}</p>
            <ul class="container-lista">
                <li v-for="red in redesSociales" :key="red.id"> 
                    <!-- Aqui estamos haciendo un v-for sobre los iconos, dandoles tamaño tambien-->
                    <a :href="red.url" target="_blank" download="CV"><img class="icon-redsocial" :src="red.src" width="40rem" :alt="red.name" ></a>
                </li>
            </ul>
            <h3>📲Celular: {{ telefono }}</h3>
            <h4>{{ residencia }}</h4>
        </div>
    </section>
</template>

<style scoped>

h1 {
  font-size: 2.5rem;
}

p {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.card {
  background-color: rgb(28, 41, 52);
  border-radius: 10px;
  padding: 10px;
  margin: 10px;
  text-align: center;
}

.container-lista {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;
}

.icon-redsocial {
  align-items: center;
  background-color: aliceblue;
  border-radius: 50%;
  padding: 2px;
  margin: 5px;
  box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}

.icon-redsocial:hover {
  background-color: rgb(28, 41, 52);
  box-shadow: 0 0 5px rgba(251, 249, 249, 0.934);
}

h3 {
  font-size: 1.2rem;
  font-weight: 600;
}

</style>