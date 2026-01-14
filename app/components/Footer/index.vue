<template>
    <PageContainer>
        <footer class="flex flex-col">
            <div class="flex justify-between items-center py-20">
                <img src="/images/brands/ricky-and-morty-logo.png" />
                <BanckToTop/>
            </div>
            <div class="flex justify-between border-t-2 py-6">
                <p>&copy; 2025</p>
                <p class="flex gap-1"><span><Code/></span>Desenvolvido por <span class="text-[#11b0c8] font-bold">MATEUS</span></p>
            </div>
        </footer>
    </PageContainer>
</template>

<script setup>
import Code from '../Icons/Code.vue';
</script>