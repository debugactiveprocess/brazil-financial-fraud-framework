<template>
    <div class="bg-ctid-navy text-white">
        <div class="xl:max-w-[1536px] mx-auto p-16 xl:py-20 lg:px-32 2xl:px-16 xl:flex">
            <div class=" xl:w-1/2 xl:pr-10">
                <h1>
                    <router-link to="/">
                        <h1>Matriz Brasileira de Fraudes Financeiras</h1>
                    </router-link>
                </h1>
                <p class="my-4">
                    Projeto comunitário e independente para documentar táticas e técnicas de fraudes financeiras no
                    Brasil. Inspirado por estruturas abertas como ATT&CK e Fight Fraud Framework, sem afiliação oficial.
                </p>
                <div class="md:flex">
                    <div class="social-links">
                        <a href="https://github.com/debugactiveprocess/brazil-financial-fraud-framework" target="blank" class="github"
                            aria-label="github do projeto">
                            <i class="pi pi-github"></i>
                        </a>
                    </div>
                </div>
            </div>
            <div class="xl:max-w-1/2 xl:pl-10 xl:my-auto mt-8">
                <div class="flex w-full  content-between">
                    <div class="w-1/2">
                        <h2 class="mt-8">Sobre</h2>
                        <ul>
                            <li><router-link to="/about/methodology">Metodologia</router-link></li>
                            <li><router-link to="/about/contributors">Contribuidores</router-link></li>
                            <li><router-link to="/about/contact-us">Contato</router-link></li>
                        </ul>
                    </div>
                    <div class="w-1/2">
                        <h2 class="mt-8">Recursos</h2>
                        <ul>
                            <li><router-link to="/matrix">Matriz</router-link></li>
                            <li><router-link to="/tactic">Táticas</router-link></li>
                            <li><router-link to="/technique">Técnicas</router-link></li>
                        </ul>
                    </div>
                </div>
                <p class="my-4 public-release">© 2026 Projeto Matriz Brasileira de Fraudes Financeiras. Conteúdo sob Apache-2.0, salvo indicação em contrário.</p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    data() {
        return {
            links: [
                { label: "Repositório", route: "https://github.com/debugactiveprocess/brazil-financial-fraud-framework" },
                { label: "Issues", route: "https://github.com/debugactiveprocess/brazil-financial-fraud-framework/issues" },
            ],
        };
    },
});
</script>

<style scoped>
h1 {
    @apply text-3xl font-medium
}

h2 {
    @apply text-xl font-semibold mt-0
}

.public-release {
    @apply text-sm mb-0
}

.social-links {
    @apply flex md:ml-8 md:my-0 my-4 gap-6 xl:gap-4 2xl:gap-8
}

.social-links a {
    @apply bg-ctid-light-blue hover:bg-white text-ctid-navy rounded-full flex h-8 w-8 my-auto text-center;
}

.social-links i {
    @apply m-auto;

}

ul {
    @apply list-inside;
    list-style-type: square;
}

li a {
    @apply hover:underline hover:text-ctid-light-blue
}
</style>