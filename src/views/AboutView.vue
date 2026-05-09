<template>
  <div class=" flex h-full flex-col-reverse md:flex-row">
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
      <h1>Sobre</h1>

      <p>A Matriz Brasileira de Fraudes Financeiras é um framework aberto para modelar golpes financeiros com
        granularidade operacional brasileira. Ela foi inspirada por modelos como ATT&CK e Fight Fraud Framework, mas é
        independente e focada em contextos locais como PIX, boleto, WhatsApp, consignado, bets, marketplaces, delivery,
        maquininhas, contas laranja e cash-out por cripto/P2P.</p>

      <h2>Metodologia</h2>
      <p>O framework usa táticas para representar objetivos do fraudador e técnicas para representar ações observáveis.
        Cada técnica busca documentar descrição, canais usados, alvos comuns, pré-requisitos, sinais observáveis,
        detecção, mitigação, evidências úteis e relações com F3/MITRE ATT&CK quando aplicável.</p>
      <router-link to="/about/methodology" class="link-blue-external small">Saiba mais</router-link>

      <h2>Contribuições</h2>
      <p>O objetivo é permitir colaboração de profissionais de antifraude, segurança, prevenção a perdas, AML, bancos,
        fintechs, varejo, adquirentes, plataformas digitais e pesquisadores independentes.</p>
      <router-link to="/about/contributors" class="link-blue-external small">Saiba mais</router-link>

      <h2>Aviso de independência</h2>
      <p>Este projeto é independente e não é afiliado, endossado ou mantido pela MITRE, pelo Center for
        Threat-Informed Defense ou pelo projeto Fight Fraud Framework.</p>
      <router-link to="/about/contact-us" class="link-blue-external small">Contato</router-link>

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
