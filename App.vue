<script>
import MainBtn from './components/MainBtn.vue'
import HoverLine from './components/HoverLine.vue'

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
      imgHeroDT: 'DT:bg-[url(@/assets/images/desktop/image-hero.jpg)]',
      isNavOpen: false,
      navData: [
        {
          text: 'about',
          isHovered: false,
        },
        {
          text: 'careers',
          isHovered: false,
        },
        {
          text: 'events',
          isHovered: false,
        },
        {
          text: 'products',
          isHovered: false,
        },
        {
          text: 'support',
          isHovered: false,
        },
      ],
      articleData: [
        {
          textArr: ['Deep', 'earth'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-deep-earth.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-deep-earth.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Night', 'arcade'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-night-arcade.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-night-arcade.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Soccer', 'team VR'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-soccer-team.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-soccer-team.jpg)]',
          isHovered: false
        },
        {
          textArr: ['The', 'grid'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-grid.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-grid.jpg)]',
          isHovered: false
        },
        {
          textArr: ['From up', 'above VR'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-from-above.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-from-above.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Pocket', 'borealis'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-pocket-borealis.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-pocket-borealis.jpg)]',
          isHovered: false
        },
        {
          textArr: ['The', 'curiosity'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-curiosity.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-curiosity.jpg)]',
          isHovered: false
        },
        {
          textArr: ['Make it', 'fisheye'],
          bgMB: 'bg-[url(@/assets/images/mobile/image-fisheye.jpg)]',
          bgDT: 'DT:bg-[url(@/assets/images/desktop/image-fisheye.jpg)]',
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
    MainBtn,
    HoverLine
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
    <header
      :class="` relative flex flex-col w-full max-w-[425px] DT:max-w-[1920px] h-[650px] ${imgHeroMB} ${imgHeroDT} bg-cover bg-center DT:bg-top px-6 DT:px-[165px] pt-10 DT:pt-16`">
      <!-- Dark Layer -->
      <div class=" absolute left-0 top-0 w-full h-full bg-neo-black bg-opacity-40 pointer-events-none z-0"></div>
      <nav class=" flex justify-between items-center">
        <img class=" relative h-6 DT:h-8 select-none z-30" :src="logo" alt="logo" draggable="false">
        <button @click="isNavOpen = !isNavOpen" class=" relative DT:hidden z-30">
          <navHamburger v-show="!isNavOpen" />
          <navClose v-show="isNavOpen" />
        </button>
        <!-- Nav Mobile -->
        <div v-show="isNavOpen"
          class=" absolute left-0 top-0 flex DT:hidden flex-col justify-center items-start gap-6 w-full h-[667px] px-6 bg-neo-black select-none z-20">
          <button v-for="item in navData"
            class=" text-neo-white hover:text-neo-dark-gray text-[24px] leading-[25px] font-light uppercase">
            {{ item.text }}
          </button>
        </div>
        <!-- Nav Desktop -->
        <div class=" relative hidden DT:flex gap-8 select-none z-30">
          <div v-for="item in navData" @mouseenter="item.isHovered = true" @mouseleave="item.isHovered = false"
            class=" relative flex flex-col items-center">
            <button class=" text-neo-white text-[15px] leading-[25px] font-alata capitalize">
              {{ item.text }}
            </button>
            <HoverLine :conditional-val="item.isHovered" />
          </div>
        </div>
      </nav>
      <div class=" absolute top-0 left-0 flex items-center w-full h-full px-6 DT:pt-24 DT:px-[165px] z-10">
        <h1
          class=" DT:w-[58%] p-6 DT:p-10 text-neo-white text-[40px] DT:text-[72px] leading-[38px] DT:leading-[70px] font-light uppercase border-neo-white border-2">
          Immersive experiences that deliver</h1>
      </div>
    </header>
    <main
      class=" flex flex-col gap-24 DT:gap-[184px] w-full max-w-[425px] DT:max-w-[1920px] my-24 DT:mt-40 DT:mb-[184px]">
      <section class=" relative flex flex-col gap-12 mx-6 DT:mx-[165px]">
        <img class=" DT:hidden select-none" :src="imgInteractiveMB" alt="imgInteractiveMB" draggable="false">
        <img class=" hidden DT:block w-[66%] select-none" :src="imgInteractiveDT" alt="imgInteractiveDT"
          draggable="false">
        <div
          class=" DT:absolute DT:right-0 DT:bottom-[-2px] flex flex-col gap-4 DT:w-[48.75%] px-6 DT:pt-24 DT:pl-24 DT:pr-0 DT:bg-neo-white text-center DT:text-left">
          <h2 class=" text-[32px] DT:text-[48px] leading-[32px] DT:leading-[48px] font-light uppercase">
            The leader in interactive VR</h2>
          <p class=" text-neo-black text-opacity-50 text-[15px] leading-[25px] font-alata">
            Founded in 2011, Loopstudios has been producing world-class virtual reality
            projects for some of the best companies around the globe. Our award-winning
            creations have transformed businesses through digital experiences that bind
            to their brand.
          </p>
        </div>
      </section>
      <section class=" flex flex-col px-6 DT:px-[165px]">
        <div class=" flex justify-center DT:justify-between mb-12 DT:mb-20">
          <h2 class=" text-[32px] DT:text-[48px] leading-[32px] DT:leading-[48px] font-light uppercase">
            Our creations</h2>
          <MainBtn class=" hidden DT:block" b-text="See all" />
        </div>
        <div class=" grid grid-cols-1 DT:grid-cols-4 gap-6 DT:gap-[30px]">
          <article v-for="item in articleData" @mouseenter="item.isHovered = true" @mouseleave="item.isHovered = false"
            :class="` relative flex flex-col justify-end w-full h-[120px] DT:h-[450px] p-5 ${item.bgMB} ${item.bgDT} bg-cover bg-top cursor-pointer`">
            <div :class="` absolute top-0 left-0 w-full h-full bg-white ${setState(item.isHovered).bgOpacity}`">
            </div>
            <h4 v-for="subItem in item.textArr"
              :class="` ${setState(item.isHovered).textColor} text-[24px] DT:text-[32px] leading-[24px] DT:leading-[32px] font-light uppercase select-none`">
              {{ subItem }}</h4>
          </article>
        </div>
        <MainBtn class=" DT:hidden mt-9" b-text="See all" />
      </section>
    </main>
    <footer
      class=" flex flex-col DT:flex-row gap-12 DT:justify-between items-center w-full max-w-[425px] DT:max-w-[1920px] DT:px-[165px] py-14 DT:pt-11 DT:pb-8 bg-neo-black">
      <div class=" flex flex-col items-center DT:items-start gap-8 DT:gap-[14px] select-none">
        <img class=" h-6" :src="logo" alt="logo">
        <div class=" flex flex-col DT:flex-row gap-4 text-neo-white text-[15px] leading-[25px] font-alata">
          <div v-for="item in footerData" @mouseenter="item.isHovered = true" @mouseleave="item.isHovered = false"
            class=" relative flex flex-col items-center">
            <a href="#" target="_blank">{{ item.text }}</a>
            <HoverLine :conditional-val="item.isHovered" />
          </div>
        </div>
      </div>
      <div class=" flex flex-col items-center DT:items-end gap-4 DT:gap-[14px]">
        <div class=" flex items-center gap-4 select-none">
          <div v-for="(item, index) in networkData" @mouseenter="item.isHovered = true"
            @mouseleave="item.isHovered = false" class=" relative cursor-pointer">
            <img :class="` ${item.hSize}`" :src="item.icon" :alt="` image ${index + 1}`">
            <HoverLine :conditional-val="item.isHovered" />
          </div>
        </div>
        <h5 class=" text-neo-white text-opacity-50">
          © 2021 Loopstudios. All rights reserved.</h5>
      </div>
    </footer>
  </body>
</template>