<template>
  <div class="text-white">
    <h1 class="text-purple-600">Teste</h1>

    <div class="flex flex-wrap w-full max-w-[1224px] gap-4 mx-auto">
      <div v-for="currentCharacter of data.results" class="bg-[#313234] rounded-lg p-4 gap-4 flex flex-col max-w-[294px]">
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

        <NuxtLink :to="currentCharacter.url" 
          class="mt-2 self-end bg-[#11b0c8] gap-2 flex py-[6px] px-1 rounded-[32px] text-sm items-center mt-auto"
          target="_blanck"
        >
          <Info/>
          Saiba Mais
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import Info from './components/Icons/info.vue';

const { data, status, error, refresh, clear } = await useFetch('https://rickandmortyapi.com/api/character')
</script>