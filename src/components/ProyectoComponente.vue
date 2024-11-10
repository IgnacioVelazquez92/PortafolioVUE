<script setup>

// Este componente muestra una galería de proyectos con información detallada sobre cada uno.
// Importamos 'ref' de Vue para crear referencias reactivas.
import { ref } from 'vue';

// 'misProyectos' es una referencia reactiva que contiene la lista de proyectos.
var misProyectos = ref([]);

// Asignamos un array de objetos a 'misProyectos.value', donde cada objeto representa un proyecto con sus detalles.
misProyectos.value = [
{
    title: "Polaris 3D SSR",
    subtitle: "Node & ExpressJS",
    description:
      "Este proyecto fue desarrollado para un  curso que desarrolle en Digit@lers TELECOM. Desarrollo de aplicaciones con node JS Claves de usuarios encriptadas con bcrypt autenticación con JWT, express sessión y envío de mail a usuarios con nodemailer",
    image: "/public/giffs/Polaris3D.gif",
    link: "http://polaris3d.onrender.com/",
    repoBack: "https://github.com/IgnacioVelazquez92/backexpress-hbs",
  },
  {
    title: "NPS Startek",
    subtitle: "MERN Stack & Firebase",
    description:
      "Este proyecto fue desarrollado para mi empresa con el objetivo de optimizar el proceso de medición del Net Promoter Score (NPS) en el contexto de nuestro cliente TELECOM. Utilicé la plataforma Firebase para alojar los archivos como imagenes, audios y MongoDB para almacenar las encuestas.",
    image: "/public/giffs/startek.gif",
    link: "https://startek.netlify.app/",
    repoFront: "https://github.com/IgnacioVelazquez92/startek-nps-front.git",
    repoBack: "https://github.com/IgnacioVelazquez92/startek-nps-back.git",
  },
  {
    title: "Lab9",
    subtitle: "DeisyUI TailwindCSS Redux-Toolkit",
    description:
      "Este proyecto web Lo tuve que realizar en 6 días para mi primer entrevista para una empresa llamada lab9, donde tenia que aplicar: react-router-dom redux-toolkit y ademas utilizar la libreria deysyUI para los componentes.",
    image: "/public/giffs/entrevista.gif",
    link: "https://entrevistalab9.netlify.app/",
    repoFront: "https://github.com/IgnacioVelazquez92/Lab9-entrevista.git",
    repoBack: "https://github.com/IgnacioVelazquez92/entrevista-lab9-back.git",
  },
  {
    title: "AM-Creaciones",
    subtitle: "MERN Stack",
    description:
      "Este proyecto, un eCommerce, se desarrolló como proyecto final durante mi formación en Rolling Code School. Fue construido empleando tecnologías esenciales como Express, Express Validator, Bcrypt, JWT y Email.js, y utilizó MongoDB junto con el framework Mongoose para gestionar la base de datos.",
    image: "/public/giffs/am-creaciones.gif",
    link: "https://am-creaciones.netlify.app",
    repoFront: "https://github.com/IgnacioVelazquez92/AM-FRONT-PF.git",
    repoBack: "https://github.com/andimenendez/proyectoFinal-backend.git",
  }
];
</script>

<template>
    <div class="galeria">
      <!-- Verifica si 'misProyectos' tiene elementos antes de iterar -->
      <li
        v-for="(proyecto, index) in misProyectos"
        :key="index"
        class="proyecto"
      >
        <img :src="proyecto.image" :alt="proyecto.title" />
        <div class="proyecto-info">
          <h3>{{ proyecto.title }}</h3>
          <p>{{ proyecto.description }}</p>
          <div class="proyecto-links">
            <a
              v-if="proyecto.link"
              :href="proyecto.link"
              class="btn-ver-mas"
              target="_blank"
              rel="noopener noreferrer"
            >Ver Proyecto</a>
            <a
              v-if="proyecto.repoFront"
              :href="proyecto.repoFront"
              class="github-link"
              target="_blank"
              rel="noopener noreferrer"
            >Ver Código en GitHub (Front)</a>
            <a
              v-if="proyecto.repoBack"
              :href="proyecto.repoBack"
              class="github-link"
              target="_blank"
              rel="noopener noreferrer"
            >Ver Código en GitHub (Back)</a>
          </div>
        </div>
      </li>
    </div>
  </template>

<style scoped>
/* Estilos para la galería de proyectos */
.galeria {
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    padding: 20px;
    justify-content: center;
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
}

/* Animación del fondo de la galería */
@keyframes gradient {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}

/* Estilos para el contenedor individual de cada proyecto */
.proyecto {
    display: flex;
    flex-direction: column;
    border: 2px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    background-color: #f9f9f9;
    max-width: 222px;
    flex: 1 1 300px;
}

/* Estilo de las imágenes del proyecto */
.proyecto img {
    width: 100%;
    height: auto;
    display: block;
}

/* Estilos para la información del proyecto */
.proyecto-info {
    padding: 15px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    text-align: center;
    height: 100%;
}

/* Estilos para el título del proyecto */
.proyecto-info h3 {
    margin: 10px 0;
    font-size: 1.3em;
    color: #333;
}

/* Estilos para la descripción del proyecto */
.proyecto-info p {
    margin: 10px 0;
    font-size: 1em;
    color: #666;
    flex-grow: 1;
}

/* Contenedor de enlaces y botones del proyecto */
.proyecto-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
}

/* Estilo del botón "Ver Más" */
.proyecto-links .btn-ver-mas {
    background-color: #007BFF;
    color: #fff;
    padding: 10px 15px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.3s;
}

/* Estilo al pasar el cursor sobre el botón "Ver Más" */
.proyecto-links .btn-ver-mas:hover {
    background-color: #0056b3;
}

/* Estilo del enlace a GitHub */
.proyecto-links .github-link {
    color: #333;
    text-decoration: none;
    font-size: 0.9em;
}

/* Estilo al pasar el cursor sobre el enlace a GitHub */
.proyecto-links .github-link:hover {
    text-decoration: underline;
}
</style>