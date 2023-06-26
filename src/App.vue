<script setup>
import { ref } from 'vue';

let conteoLikes=ref(0);
let limitante=0;
let conteoDislikes=ref(0);
let love=document.querySelector('.love')
let gw=document.querySelector('.gw')

const like=function(){
  if(limitante<=0){
    conteoLikes.value++;
    conteoDislikes.value--;
  }
  if(limitante==0){
    conteoDislikes.value++;
  }
  limitante=1;
  love.setAttribute("fill","red")
  gw.setAttribute("fill","none")
}

const dislike=function(){
  if(limitante>=0){
    conteoDislikes.value++;
    conteoLikes.value--;
  }
  if(limitante==0){
    conteoLikes.value++;
  }
  limitante=-1;
  gw.setAttribute("fill","green")
  love.setAttribute("fill","none")
}

</script>

<template>
  <div class=" ml-[500px] mr-[500px] bg-white border-[5px] border-gray-400">
    <div class="flex justify-between mt-5">
      <h2 class="ml-4 font-bold">
        historias
      </h2>
      <div class="p-1 mr-4 text-white bg-blue-400 rounded-lg">
        todas
      </div>
    </div>
    
    <div class="flex justify-between mx-40">
      <img src="https://www.mundodeportivo.com/alfabeta/hero/2021/08/Terraria-disponible-para-Android-iOS-y-Steam.jpg?width=1200" class=" w-[100px] h-[100px] object-cover border-[4px] rounded-xl border-blue-300" alt="">
      <img src="https://static.bandainamcoent.eu/high/elden-ring/elden-ring/00-page-setup/elden-ring-new-header-mobile.jpg" class="w-[100px] h-[100px] object-cover border-[4px] rounded-xl border-blue-300" alt="">
      <img src="https://support.activision.com/resource/1553213708000/Sekiro_Content_sidebanner" class=" w-[100px] h-[100px] object-cover border-[4px] rounded-xl border-blue-300" alt="">
      <img src="https://cdn.hobbyconsolas.com/sites/navi.axelspringer.es/public/media/image/2016/02/566054-plants-vs-zombies-garden-warfare-2-analisis-ps4-xbox-one-pc.jpg?tf=3840x" class=" w-[100px] h-[100px] object-cover border-[4px] rounded-xl border-blue-300" alt="">
    </div>
    <div class="relative flex items-center mx-7">
      <div >
        <img src="https://www.diariodenavarra.es/uploads/2017/12/20/60b0e40619dd6.jpeg" class=" h-[45px] w-[45px] rounded-full" alt="">
      </div>
      <div class="mt-3 ml-5">
        <h2 class="font-bold ">
          Miyazaki Bueno
        </h2>
        <h3>
          hace 10 minutos
        </h3>
      </div>
      <i class="absolute right-0 text-red-700"> 
        reportar
      </i>
    </div>
    <div class="mt-5 mx-7">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg/528px-Big_Floppa_and_Justin_2_%28cropped%29.jpg" class="w-full mx-auto rounded-3xl" alt="">
    </div>
    <div class="flex mt-3 mx-7">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 ml-7 hover:text-red-600" ref="love" @click="like">
        <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
      </svg>
      <p>{{ conteoLikes }}</p>
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 ml-5 hover:text-gray-700" ref="gw" @click="dislike">
        <path stroke-linecap="round" stroke-linejoin="round" d="M7.5 15h2.25m8.024-9.75c.011.05.028.1.052.148.591 1.2.924 2.55.924 3.977a8.96 8.96 0 01-.999 4.125m.023-8.25c-.076-.365.183-.75.575-.75h.908c.889 0 1.713.518 1.972 1.368.339 1.11.521 2.287.521 3.507 0 1.553-.295 3.036-.831 4.398C20.613 14.547 19.833 15 19 15h-1.053c-.472 0-.745-.556-.5-.96a8.95 8.95 0 00.303-.54m.023-8.25H16.48a4.5 4.5 0 01-1.423-.23l-3.114-1.04a4.5 4.5 0 00-1.423-.23H6.504c-.618 0-1.217.247-1.605.729A11.95 11.95 0 002.25 12c0 .434.023.863.068 1.285C2.427 14.306 3.346 15 4.372 15h3.126c.618 0 .991.724.725 1.282A7.471 7.471 0 007.5 19.5a2.25 2.25 0 002.25 2.25.75.75 0 00.75-.75v-.633c0-.573.11-1.14.322-1.672.304-.76.93-1.33 1.653-1.715a9.04 9.04 0 002.86-2.4c.498-.634 1.226-1.08 2.032-1.08h.384" />
      </svg>
      <p>{{ conteoDislikes }}</p>
    </div>
    <div class="flex justify-between p-2 mx-20 mt-3 bg-gray-300 rounded-xl">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 ml-10 text-blue-400 fill-current">
        <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z" />
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-blue-400 fill-current">
        <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 mr-10 text-blue-400 fill-current">
        <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" />
      </svg>

    </div>
  </div>
</template>