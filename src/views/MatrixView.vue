<template>
    <breadcrumb-component :breadcrumbItems="breadcrumbItems" class="mt-0" />
    <div>
        <h1>Matriz Brasileira de Fraudes Financeiras</h1>
        <p>A matriz mostra a relação entre táticas e técnicas usadas em golpes financeiros no Brasil. As táticas
            representam objetivos do fraudador e as técnicas representam ações observáveis que podem apoiar prevenção,
            detecção, resposta, investigação e compartilhamento de inteligência antifraude.
        </p>
    </div>
    <div class="mt-8">
        <matrix-container />
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MatrixContainer from "../components/MatrixContainer.vue";
import BreadcrumbComponent from "../components/BreadcrumbComponent.vue";

export default defineComponent({
    components: { BreadcrumbComponent, MatrixContainer },
    data() {
        return {
            breadcrumbItems: [
                { label: "Resources", route: "/resources" },
                { label: "Matrix", route: "/matrix" }
            ],
        }
    }
});
</script>

<style scoped></style>
