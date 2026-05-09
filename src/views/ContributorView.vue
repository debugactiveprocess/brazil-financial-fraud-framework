<template>
  <div class="flex h-full flex-col-reverse md:flex-row">
    <div class="sidebar">
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
    </div>
    <div class="main">
      <breadcrumb-component :breadcrumbItems="breadcrumbItems" class="mb-2 -ml-3" />
      <h1>Contribuidores</h1>

      <p>Este projeto está em versão inicial e preparado para receber contribuições de profissionais e pesquisadores de
        antifraude, segurança, AML, prevenção a perdas, bancos, fintechs, adquirentes, varejo, marketplaces e
        plataformas digitais.</p>

      <p>Para contribuir, abra uma issue ou pull request com descrições defensivas, sinais observáveis, detecções,
        mitigações, evidências úteis e exemplos brasileiros devidamente anonimizados.</p>

      <router-link to="/about/contact-us" class="link-blue-external small">Como contribuir</router-link>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import BreadcrumbComponent from "../components/BreadcrumbComponent.vue";

export default defineComponent({
  components: { BreadcrumbComponent },

  data() {
    return {
      breadcrumbItems: [
        { label: "About", route: "/about" },
        { label: "Project Contributors", route: "/about/contributors" },
      ],
    };
  },
  computed: {
  }
})

</script>

<style scoped>
.main {
  @apply w-full block
}

a h3 {
  @apply text-ctid-blue hover:text-ctid-navy
}

.contributor {
  @apply flex w-full h-20
}

.contributor img {
  @apply m-auto h-20 w-auto object-contain
}
</style>
