<template>
    <section class="flex flex-col gap-8 items-center max-w-[1224px] w-full mx-auto xl:items-start text-white">
        <ListingHeader title="Episódios"/>
        <div class="flex flex-wrap gap-4 justify-center">
            <Card v-for="currentEpisode in data.results" class="flex flex-col gap-2 justify-between">
                <div class="flex gap-2 items-center">
                    <Play/>
                    <p>{{ currentEpisode.name }} | {{ currentEpisode.id }}</p>
                </div>
                <div class="flex items-center justify-between">
                    <SeeDocumentDetails/>
                    <HeartFilled/>
                </div>
            </Card>
        </div>
    </section>
</template>

<script setup>
const { data, status, error, refresh, clear } = await useFetch('https://rickandmortyapi.com/api/character')

console.log(data.value.results)
</script>