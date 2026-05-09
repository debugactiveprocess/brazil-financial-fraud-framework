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
      <h1>Histórico de versões</h1>
      <p>A Matriz Brasileira de Fraudes Financeiras usa versionamento major.minor. Versões major indicam mudanças
        relevantes na taxonomia, táticas ou técnicas. Versões minor indicam correções, ajustes de texto ou novos
        conteúdos incrementais.</p>
      <h2>Versão atual</h2>
      <div class="version">
        <div class="w-1/2 my-auto">
          <h3>BR Fraud Framework v0.1</h3>
          <p>Maio de 2026 - Atual</p>
        </div>

        <div class="grid grid-cols-2 w-1/2">
          <a :href="stixUrl" download="br-fraud-stix-v1" class="link-blue-external small">Download
            STIX</a>
          <a :href="navigatorUrl" download="br-fraud-navigator-v1" class="link-blue-external small">Download
            Navigator Layer</a>
          <a :href="jsonUrl" download="br-fraud-json-v1" class="link-blue-external small">Download JSON</a>
        </div>

      </div>

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
        { label: "Version History", route: "/resources/versions" },
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

.version {
  @apply border-ctid-light-gray border-[1px] py-4 px-6 my-1 flex
}

.version h3 {
  @apply font-medium normal-case text-lg
}
</style>
