<script>
export default {
   data() {
      return {

      }
   },
   props: {
      bText: {
         String,
         default: 'Empty',
      }
   }
}
</script>
<template>
   <button
      class=" self-center w-[157px] h-10 hover:bg-neo-black hover:text-neo-white text-[14px] leading-[14px] tracking-[5px] font-alata uppercase border-neo-black border-[1px] select-none">
      {{ bText }}
   </button>
</template>