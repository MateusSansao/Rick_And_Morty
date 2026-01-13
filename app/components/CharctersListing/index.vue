<template>
    <section class="flex flex-col gap-8 text-white bg-[#1e1e1e] max-w-[1224px] w-full mx-auto">
      <div class="flex flex-wrap gap-4 justify-center xl:justify-start">

        <ListingHeader title="Personagens"/>

        <div class="flex flex-wrap gap-4 justify-center">
          <Card v-for="currentCharacter of data.results">
            <img :src="currentCharacter.image" height="200" width="262" class="rounded-2xl h-[200px]">

            <div class="grid grid-cols-[1fr_48px]">
              <div class="flex flex-col gap-4">
                <p class="text-base font-bold">{{ currentCharacter.name }}</p>

                <div class="flex flex-col gap-2">  
                  <p>{{ currentCharacter.status === 'Alive' ? 'Vivo' : 'Morto'}}</p>
                  <p>{{ currentCharacter.species }}</p>
                  <p>{{ currentCharacter.origin.name }}</p>
                </div>
              </div>
              <span>
                <IconsHeartFilled v-if="currentCharacter.status === 'Alive' "/>
                <IconsHeartOutlined v-else/>
              </span>
            </div>

            <SeeDocumentDetails :id="currentCharacter.id"/>
          </Card>
        </div>
      </div>
    </section>
</template>

<script setup>
const { data } = await useFetch('https://rickandmortyapi.com/api/character')
</script>