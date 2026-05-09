<template>
  <div class="flex h-full flex-col-reverse md:flex-row">
    <div class="sidebar">
      <h2>Nesta página</h2>
      <h3 @click="scrollToHeading('visao-geral')" class="cursor-pointer">Visão geral</h3>
      <h3 @click="scrollToHeading('modelo')" class="cursor-pointer">Modelo</h3>
      <h3 @click="scrollToHeading('criterios')" class="cursor-pointer">Critérios</h3>
      <h3 @click="scrollToHeading('uso')" class="cursor-pointer">Uso defensivo</h3>
    </div>
    <div class="main">
      <breadcrumb-component :breadcrumbItems="breadcrumbItems" class="mb-2 -ml-3" />

      <h1>Metodologia</h1>

      <h2 id="visao-geral">Visão geral</h2>
      <p>
        A Matriz Brasileira de Fraudes Financeiras organiza comportamentos observáveis de fraudadores em táticas e técnicas.
        O foco é documentar a realidade operacional brasileira, incluindo PIX, boleto, WhatsApp, falsas centrais, marketplaces,
        contas laranja, bets, cripto/P2P, maquininhas e outros canais locais.
      </p>
      <p>
        O projeto é independente e usa frameworks globais apenas como referência conceitual para manter linguagem estruturada,
        interoperável e útil para equipes de prevenção, detecção, resposta e investigação.
      </p>

      <h2 id="modelo">Modelo</h2>
      <p>
        As táticas representam objetivos do fraudador. As técnicas representam ações usadas para alcançar esses objetivos.
        Cada técnica busca registrar nome local, nome global em inglês, descrição, canais usados, alvos comuns, pré-requisitos,
        sinais observáveis, detecção, mitigação, evidências úteis e relações com F3/MITRE ATT&amp;CK quando aplicável.
      </p>
      <ul>
        <li>
          <strong>Táticas:</strong> Preparação, Aproximação, Engenharia Social, Comprometimento, Manipulação de Pagamento,
          Execução Financeira, Cash-out/Lavagem, Evasão/Encobrimento e Revitimização.
        </li>
        <li>
          <strong>Técnicas:</strong> ações observáveis como falso comprovante PIX, QR Code adulterado, falsa central bancária,
          falso motoboy e conta laranja alugada.
        </li>
      </ul>

      <h2 id="criterios">Critérios para inclusão</h2>
      <ul>
        <li>A técnica deve representar comportamento observável do fraudador.</li>
        <li>Deve ter utilidade defensiva, investigativa ou de inteligência.</li>
        <li>Deve se relacionar com fraude financeira no contexto brasileiro.</li>
        <li>Deve evitar detalhes sensíveis, dados pessoais ou instruções operacionais abusivas.</li>
        <li>Deve incluir sinais observáveis, detecção, mitigação e evidências úteis sempre que possível.</li>
      </ul>

      <h2 id="uso">Uso defensivo</h2>
      <p>
        A matriz pode apoiar triagem de incidentes, criação de regras antifraude, treinamento, análise de cadeia de golpe,
        investigação financeira, resposta a incidentes, compartilhamento de inteligência e priorização de controles.
      </p>
      <p>
        Exemplo de cadeia modelada: anúncio falso em rede social → conversa no WhatsApp → QR Code PIX ou chave aleatória →
        falso comprovante → conta laranja → cash-out via bet/cripto/P2P → revitimização de contatos.
      </p>
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
        { label: "Metodologia", route: "/about/methodology" },
      ],
    };
  },
  methods: {
    scrollToHeading(id: string) {
      document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
    },
  },
});
</script>

<style scoped>
a h3,
h3 {
  @apply text-ctid-blue hover:text-ctid-navy;
}

ul {
  @apply ml-6 list-disc my-4;
}

li {
  @apply my-2;
}
</style>
