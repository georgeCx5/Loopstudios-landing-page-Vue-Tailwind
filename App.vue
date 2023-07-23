<script>
// import imgHeroMB from '@/assets/images/mobile/image-hero.jpg'
import logo from '@/assets/images/logo.svg?url'
import navHamburger from '@/assets/images/icon-hamburger.svg?component'
import navClose from '@/assets/images/icon-close.svg?component'

export default {
  data() {
    return {
      logo,
      imgHeroMB: 'bg-[url(@/assets/images/mobile/image-hero.jpg)]',
      isNavOpen: false,
      navData: [
        'about',
        'careers',
        'events',
        'products',
        'support'
      ]
    }
  },
  components: {
    navHamburger,
    navClose,
  }
}
</script>
<template>
  <body class=" flex flex-col items-center text-neo-black font-josefin">
    <header :class="` relative flex flex-col w-full max-w-[425px] h-[650px] ${imgHeroMB} bg-cover bg-center px-6 pt-10`">
      <nav class=" flex justify-between items-center">
        <img class=" relative h-6 select-none z-20" :src="logo" alt="logo" draggable="false">
        <button @click="isNavOpen = !isNavOpen" class=" relative DT:hidden z-20">
          <navHamburger v-show="!isNavOpen" />
          <navClose v-show="isNavOpen" />
        </button>
        <div v-show="isNavOpen"
          class=" absolute left-0 top-0 flex flex-col justify-center items-start gap-6 w-full h-[667px] px-6 bg-neo-black select-none z-10">
          <button v-for="item in navData"
            class=" text-neo-white hover:text-neo-dark-gray text-[24px] leading-[25px] font-light uppercase">
            {{ item }}
          </button>
        </div>
      </nav>
      <div class=" absolute top-0 left-0 flex items-center w-full h-full px-6">
        <h1 class=" p-6 text-neo-white text-[40px] leading-[38px] font-light uppercase border-neo-white border-2">
          Immersive experiences that deliver</h1>
      </div>
    </header>
    <main class=" w-full max-w-[425px]">

    </main>
    <footer class=" w-full max-w-[425px]">

    </footer>
  </body>
</template>