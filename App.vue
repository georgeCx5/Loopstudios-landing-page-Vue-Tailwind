<script>
import MainBtn from './components/MainBtn.vue'

import logo from '@/assets/images/logo.svg?url'
import navHamburger from '@/assets/images/icon-hamburger.svg?component'
import navClose from '@/assets/images/icon-close.svg?component'
import imgInteractiveMB from '@/assets/images/mobile/image-interactive.jpg'
import imgInteractiveDT from '@/assets/images/desktop/image-interactive.jpg'

import iconFacebook from '@/assets/images/icon-facebook.svg?url'
import iconTwitter from '@/assets/images/icon-twitter.svg?url'
import iconPinterest from '@/assets/images/icon-pinterest.svg?url'
import iconInstagram from '@/assets/images/icon-instagram.svg?url'

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
      ],
      articleData: [
        {
          textArr: ['Deep', 'earth'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-deep-earth.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-deep-earth.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Night', 'arcade'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-night-arcade.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-night-arcade.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Soccer', 'team VR'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-soccer-team.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-soccer-team.jpg)]',
          isHovered: false
        },
        {
          textArr: ['The', 'grid'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-grid.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-grid.jpg)]',
          isHovered: false
        },
        {
          textArr: ['From up', 'above VR'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-from-above.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-from-above.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Pocket', 'borealis'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-pocket-borealis.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-pocket-borealis.jpg)]',
          isHovered: false
        },
        {
          textArr: ['The', 'curiosity'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-curiosity.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-curiosity.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Make it', 'fisheye'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-fisheye.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/mobile/image-fisheye.jpg)]',
          isHovered: false
        }
      ],
      imgInteractiveMB,
      imgInteractiveDT,
      footerData: [
        {
          text: 'About',
          isHovered: false
        },
        {
          text: 'Careers',
          isHovered: false
        },
        {
          text: 'Events',
          isHovered: false
        },
        {
          text: 'Products',
          isHovered: false
        },
        {
          text: 'Support',
          isHovered: false
        },
      ],
      networkData: [
        {
          icon: iconFacebook,
          hSize: 'h-6',
          isHovered: false
        },
        {
          icon: iconTwitter,
          hSize: 'h-5',
          isHovered: false
        },
        {
          icon: iconPinterest,
          hSize: 'h-6',
          isHovered: false
        },
        {
          icon: iconInstagram,
          hSize: 'h-6',
          isHovered: false
        },
      ]
    }
  },
  components: {
    navHamburger,
    navClose,
    MainBtn
  },
  methods: {
    setState(state) {
      let bgOpacity
      let textColor
      if (state) {
        bgOpacity = 'bg-opacity-25'
        textColor = 'text-neo-black'
      } else {
        bgOpacity = 'bg-opacity-0'
        textColor = 'text-neo-white'
      }
      return { bgOpacity, textColor }
    },
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
          class=" absolute left-0 top-0 flex DT:hidden flex-col justify-center items-start gap-6 w-full h-[667px] px-6 bg-neo-black select-none z-10">
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
    <main class=" flex flex-col gap-24 w-full max-w-[425px] my-24">
      <section class=" flex flex-col gap-12 px-6">
        <img class=" select-none" :src="imgInteractiveMB" alt="imgInteractiveMB" draggable="false">
        <div class=" flex flex-col gap-4 px-6 text-center">
          <h2 class=" text-[32px] leading-[32px] font-light uppercase">
            The leader in interactive VR</h2>
          <p class=" text-neo-black text-opacity-50 text-[15px] leading-[25px] font-alata">
            Founded in 2011, Loopstudios has been producing world-class virtual reality
            projects for some of the best companies around the globe. Our award-winning
            creations have transformed businesses through digital experiences that bind
            to their brand.
          </p>
        </div>
      </section>
      <section class=" flex flex-col px-6">
        <h2 class=" mb-12 text-center text-[32px] leading-[32px] font-light uppercase">Our creations</h2>
        <div class=" flex flex-col gap-6 mb-9">
          <article v-for="item in articleData" @mouseenter="item.isHovered = true" @mouseleave="item.isHovered = false"
            :class="` relative flex flex-col justify-end w-full h-[120px] p-5 ${item.bgMB} bg-cover bg-center cursor-pointer`">
            <div :class="` absolute top-0 left-0 w-full h-full bg-white ${setState(item.isHovered).bgOpacity}`">
            </div>
            <h4 v-for="subItem in item.textArr"
              :class="` ${setState(item.isHovered).textColor} text-[24px] leading-[24px] font-light uppercase select-none`">
              {{ subItem }}</h4>
          </article>
        </div>
        <MainBtn b-text="See all" />
      </section>
    </main>
    <footer class=" flex flex-col gap-12 items-center w-full max-w-[425px] py-14 bg-neo-black">
      <div class=" flex flex-col items-center gap-8">
        <img class=" h-6" :src="logo" alt="logo">
        <div class=" flex flex-col gap-4 text-neo-white text-[15px] leading-[25px] font-alata">
          <div v-for="item in footerData" @mouseenter="item.isHovered = true" @mouseleave="item.isHovered = false"
            class=" relative flex flex-col items-center">
            <a href="#" target="_blank">{{ item.text }}</a>
            <Transition name="line-fade">
              <div v-show="item.isHovered" class=" absolute bottom-[-8px] w-6 h-[2px] bg-neo-white"></div>
            </Transition>
          </div>
        </div>
      </div>
      <div class=" flex flex-col items-center gap-4">
        <div class=" flex items-center gap-4">
          <div v-for="(item, index) in networkData" @mouseenter="item.isHovered = true"
            @mouseleave="item.isHovered = false" class=" relative cursor-pointer">
            <img :class="` ${item.hSize}`" :src="item.icon" :alt="` image ${index + 1}`">
            <Transition name="line-fade">
              <div v-show="item.isHovered" class=" absolute bottom-[-8px] w-full h-[2px] bg-neo-white"></div>
            </Transition>
          </div>
        </div>
        <h5 class=" text-neo-white text-opacity-50">
          © 2021 Loopstudios. All rights reserved.</h5>
      </div>
    </footer>
  </body>
</template>
<style>
.line-fade-enter-active,
.line-fade-leave-active {
  transition: opacity .33s ease;
}

.line-fade-enter-from,
.line-fade-leave-to {
  opacity: 0;
}
</style>