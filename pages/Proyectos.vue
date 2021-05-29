<template>
  <b-container class="mt-5">
    <h1 class="text-center">Proyectos</h1>
    <b-row>
      <b-col>
        <ul>
          <li v-for="proyecto in proyetos.nodes" :key="proyecto.id">
            {{ proyecto.title }} <br />
            {{ proyecto["informacionBasica"].urlDelSitio }} <br />
            {{ proyecto["uri"] }}
            <p v-html="proyecto.informacionBasica.descripcionDelProyecto"></p>
          </li>
        </ul>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import proyetos from "~/queries/proyectos/proyectos";
export default {
  apollo: {
    proyetos: {
      prefetch: true,
      query: proyetos
    }
  },
  head: {
    title: "Proyectos Bogotá Web Company"
  }
};
</script>

<style lang="scss" scoped></style>
