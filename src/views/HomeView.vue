<template>
  <main>
    <section class="hero full-bleed">
      <div class="hero-inner">
        <div class="hero-grid">
          <div class="hero-left">
            <h1 class="font-medium text-4xl">Matriz Brasileira de Fraudes Financeiras</h1>

            <div class="grid grid-cols-2 gap-x-2 gap-y-2 mt-6 w-96">
              <div v-for="link in featuredLinks" :key="link.label" class="w-32">
                <a
                  v-if="link.external"
                  :href="link.route"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="link-blue-external"
                >
                  {{ link.label }}
                </a>
                <router-link v-else :to="link.route" class="link-blue-external">
                  {{ link.label }}
                </router-link>
              </div>
            </div>
          </div>

          <div class="hero-right">
            <p>A Matriz Brasileira de Fraudes Financeiras é uma base de conhecimento comunitária e independente para
              descrever golpes financeiros observados no Brasil. O projeto organiza táticas, técnicas, sinais
              observáveis, formas de detecção, mitigação e evidências úteis para casos envolvendo PIX, boleto,
              WhatsApp, marketplaces, contas laranja, bets, cripto/P2P, maquininhas e engenharia social local.
            </p>
            <div class="mt-4 flex flex-wrap gap-20">
              <router-link to="/about" class="link-blue-external">Saiba mais</router-link>
              <router-link to="/resources" class="link-blue-external">Baixar dados</router-link>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="matrix-container">
      <h1 class="text-center font-medium text-3xl mb-6 mt-8">
        Matriz Brasileira de Fraudes Financeiras
      </h1>
      <matrix-container />
    </section>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MatrixContainer from "../components/MatrixContainer.vue";

export default defineComponent({
  components: { MatrixContainer },
  data() {
    return {
      featuredLinks: [
        {
          label: "Recursos", route: "/resources"
        },
        { label: "Contribuidores", route: "/about/contributors" },
        { label: "Táticas", route: "/tactic" },

        {
          label: "Técnicas", route: "/technique"
        }
      ] as Array<{ label: string; route: string; external?: boolean }>,
    };
  },
})
</script>
<style scoped>
.full-bleed {
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
}

/* Pull background to the top of the viewport */
.hero {
  @apply bg-ctid-light-gray/30;
  margin-top: -7rem;
  padding-top: 7rem;
  padding-bottom: 3rem;
}

/* Now this can be "normal" spacing, not huge top padding */
.hero-inner {
  @apply mx-auto w-11/12 lg:w-3/4;
  @apply py-5 sm:py-6;
}

.hero-grid {
  @apply flex flex-col lg:flex-row;
  @apply gap-10 lg:gap-16;
  @apply items-start;
}

.hero-left,
.hero-right {
  @apply w-full lg:w-1/2;
}

.matrix-container {
  @apply pt-10;
}
</style>