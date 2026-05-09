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
      <h1>Contato</h1>
      <p class="mt-6">A Matriz Brasileira de Fraudes Financeiras deve evoluir com contribuições da comunidade.</p>
      <p class="mt-6">Use issues no GitHub para sugerir novas técnicas, corrigir descrições, propor detecções,
        adicionar exemplos brasileiros ou melhorar mapeamentos com frameworks globais. Se estiver sugerindo alteração
        em uma técnica existente, inclua o nome e o ID da técnica.</p>
      <div class="flex gap-2">
        <a href="https://github.com/debugactiveprocess/brazil-financial-fraud-framework/issues/new" target="_blank"
          class="btn btn-external">Abrir issue no GitHub <i class="pi pi-external-link"></i>
        </a>
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
    return {
      breadcrumbItems: [
        { label: "Sobre", route: "/about" },
        { label: "Contato", route: "/about/contact-us" },
      ],
    };
  },
})

</script>

<style scoped>
label {
  @apply uppercase pb-0 text-lg;
  font-family: "Fira Sans Extra Condensed", sans-serif;
}

.description {
  @apply -mt-1 pt-0 text-sm mb-1
}

a h3 {
  @apply text-ctid-blue hover:text-ctid-navy
}

button {
  border-radius: 0;
  margin: auto;
  text-transform: uppercase;
  font-family: "Fira Sans Extra Condensed", sans-serif;

}
</style>
