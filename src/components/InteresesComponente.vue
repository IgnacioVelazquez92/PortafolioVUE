<script setup>

import { ref } from 'vue';
// import MatrixBackground from './Fondo/MatrixBackground.vue';
import FondoLava from './FondoLava.vue';
//Este es un arreglo con ref para que se pueda reactivar el cambio de los intereses
const intereses = ref([
    'Desarrollo backend con Java: Explorar frameworks como Spring Boot, Hibernate y Java EE para crear aplicaciones escalables y robustas.',
    'Full Stack MERN: Aprender y dominar las tecnologías del stack MERN (MongoDB, Express.js, React.js y Node.js) para desarrollar aplicaciones web completas.',
    'Bases de datos: Estudiar y aplicar conocimientos de diseño y optimización de bases de datos relacionales y no relacionales (MySQL, PostgreSQL, MongoDB, etc.).',
    'Arquitectura de software: Analizar y diseñar patrones de arquitectura como Microservicios, Monolito y Event-Driven para sistemas complejos.',
    'Seguridad y testing: Implementar prácticas de seguridad y testing en aplicaciones Java y MERN, utilizando herramientas como JUnit, TestNG, Jest y Cypress.',
    'Desarrollo de APIs RESTful: Crear y documentar APIs RESTful con Java y Node.js, siguiendo principios de diseño y estándares de industria.',
    'Integración continua y despliegue: Automatizar procesos de build, test y despliegue utilizando herramientas como Jenkins, GitLab CI/CD y Docker.',
    'Aprendizaje de tecnologías emergentes: Explorar tecnologías como Kotlin, GraphQL, WebSocket y Serverless para mantenerse actualizado en el campo.'
]);

</script>

<template>
    <div class="intereses-contenedor">
        <FondoLava />
        <ul class="contenedor-lista">
            <li class="item" v-for="interes in intereses" :key="interes">
                {{ interes }}
            </li>
        </ul>
    </div>
</template>

<style scoped>

.intereses-contenedor {
    display: flex;
    position: relative;
    margin: 0 auto;
    max-width: 85%;
    padding: 1rem;
}

.contenedor-lista {
    list-style-type: none;
    padding: 1rem;
    margin-bottom: .5rem;
    color: var(--vt-c-white-soft);
    font-size: 1.4rem;
    text-shadow: 3px 3px 6px rgba(0, 0, 0, 1);
}

.item {
    margin-bottom: 1rem;
}

</style>