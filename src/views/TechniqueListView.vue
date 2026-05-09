<template>
    <breadcrumb-component :breadcrumbItems="breadcrumbItems" />
    <div>
        <h1>Técnicas</h1>
        <p>Técnicas representam “como” o fraudador alcança um objetivo tático por meio de uma ação observável. Cada
            técnica brasileira inclui descrição, canais, alvos, pré-requisitos, sinais observáveis, detecção,
            mitigação, evidências úteis e mapeamentos quando aplicável.</p>
        <p>As técnicas brasileiras usam identificadores no formato BRF-####.</p>

        <DataTable v-model:filters="filters" :value="techniques" dataKey="id"
            :globalFilterFields="['id', 'name', 'description']" class="w-full">
            <template #header>
                <div class="flex justify-end">
                    <InputGroup>
                        <InputText size="small" variant="outline" v-model="filters['global'].value"
                            placeholder="Buscar" />
                        <InputGroupAddon>
                            <Button severity="secondary" variant="icon">
                                <i class="pi pi-search"></i>
                            </Button>
                        </InputGroupAddon>
                    </InputGroup>
                </div>
            </template>
            <Column header="ID" filterField="technique.id">
                <template #body="{ data }">
                    <router-link :to="'/technique/' + data.id">{{ data.id }}
                    </router-link>
                </template>
            </Column>
            <Column header="Nome" filterField="technique.name">
                <template #body="{ data }">
                    <router-link :to="'/technique/' + data.id">{{ data.name }}
                    </router-link>
                </template>
            </Column>
            <Column header="Descrição" filterField="technique.description" headerClass="description-col"
                bodyClass="description-col">
                <template #body="{ data }">
                    {{ getShortDescription(data) }}
                </template>
            </Column>
        </DataTable>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BreadcrumbComponent from "../components/BreadcrumbComponent.vue";
import json from "../data/matrix-data.json";
import DataTable from "primevue/datatable";
import Column from 'primevue/column';
import { FilterMatchMode } from '@primevue/core/api';
import InputText from 'primevue/inputtext';
import InputGroup from 'primevue/inputgroup';
import InputGroupAddon from 'primevue/inputgroupaddon';

export default defineComponent({
    components: { BreadcrumbComponent, DataTable, Column, InputGroup, InputGroupAddon, InputText },
    data() {
        return {
            matrixData: json,
            breadcrumbItems: [
                { label: "Resources", route: "/resources" },
                { label: "Techniques", route: "/techniques" },
            ],
            filters: {
                global: { value: null, matchMode: FilterMatchMode.CONTAINS },
            }
        }
    },
    computed: {
        techniques() {
            return this.matrixData.filter(i => !i.tactic)
        },
    },
    methods: {
        getShortDescription(technique) {
            const words = technique.description.split(' ');
            if (words.length > 50) {
                return words.slice(0, 50).join(' ') + '...';
            }
            return technique.description;
        }
    }
});
</script>

<style scoped>
.p-inputgroup {
    max-width: 200px;
}

a {
    @apply text-ctid-blue hover:text-ctid-navy hover:underline
}

/* Make the internal table fixed-width and allow wrapping */
:deep(.p-datatable-table) {
    table-layout: fixed;
    width: 100%;
}

/* Allow cell content to wrap instead of forcing a long single line */
:deep(.p-datatable-tbody > tr > td) {
    white-space: normal;
    word-break: break-word;
}

:deep(.description-col) {
    @apply w-2/3 xl:w-3/4 hidden md:table-cell
}
</style>
