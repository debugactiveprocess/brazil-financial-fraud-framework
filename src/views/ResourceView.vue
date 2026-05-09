<template>
  <div class="flex h-full flex-col-reverse md:flex-row">
    <div class="sidebar">
      <h2><router-link to="/resources">Resources</router-link></h2>
      <router-link to="/matrix">
        <h3>Matrix</h3>
      </router-link>
      <router-link to="/technique">
        <h3>Techniques</h3>
      </router-link>
      <router-link to="/tactic">
        <h3>Tactics</h3>
      </router-link>
      <h2><router-link to="/about">About</router-link></h2>
      <router-link to="/about/methodology">
        <h3>Design Principles</h3>
      </router-link>
      <router-link to="/about/contributors">
        <h3>Contributors</h3>
      </router-link>
      <router-link to="/about/contact-us">
        <h3>Contact Us</h3>
      </router-link>
    </div>
    <div class="main">
      <breadcrumb-component :breadcrumbItems="breadcrumbItems" class="mb-2 -ml-3" />
      <h1>Recursos</h1>
      <h2>Baixar dados</h2>
      <p>Os dados da matriz podem ser usados para documentação de incidentes, prevenção, detecção, investigação,
        treinamento, pesquisa e compartilhamento de inteligência antifraude.</p>
      <div class="flex gap-8"><a :href="stixUrl" download="br-fraud-stix-v1" class="link-blue-external small">Download
          STIX</a>
        <a :href="navigatorUrl" download="br-fraud-navigator-v1" class="link-blue-external small">Download
          Navigator Layer</a>
        <a :href="jsonUrl" download="br-fraud-json-v1" class="link-blue-external small">Download JSON</a>

      </div>
      <h2>Matriz</h2>
      <p>A matriz fornece uma visualização da relação entre táticas e técnicas brasileiras.
      </p>
      <router-link to="/matrix" class="link-blue-external small">Saiba mais</router-link>

      <h2>Lista de Táticas</h2>
      <p>Veja todas as táticas brasileiras, como Preparação, Engenharia Social, Manipulação de Pagamento e Cash-out/Lavagem.</p>
      <router-link to="/tactic" class="link-blue-external small">Saiba mais</router-link>

      <h2>Lista de Técnicas</h2>
      <p>Veja técnicas como falso comprovante PIX, QR Code adulterado, falsa central, falso motoboy, conta laranja e cash-out via bet.</p>
      <router-link to="/technique" class="link-blue-external small">Saiba mais</router-link>


    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import BreadcrumbComponent from "../components/BreadcrumbComponent.vue";

export default defineComponent({
  components: { BreadcrumbComponent },

  data() {
    const baseUrl = import.meta.env.BASE_URL
    return {
      stixUrl: `${baseUrl}br-fraud-stix.json`,
      navigatorUrl: `${baseUrl}br-fraud-navigator.json`,
      jsonUrl: `${baseUrl}br-fraud-v1.json`,
      breadcrumbItems: [
        { label: "Resources", route: "/resources" },
      ],
    };
  },
  computed: {
  }
})

</script>

<style scoped>
a h3 {
  @apply text-ctid-blue hover:text-ctid-navy
}
</style>
