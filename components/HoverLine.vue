<script>
export default {
   data() {
      return {

      }
   },
   props: {
      conditionalVal: {
         Boolean,
         required: true,
      }
   }
}
</script>
<template>
   <Transition name="line-fade">
      <div v-show="conditionalVal" class=" absolute bottom-[-8px] w-6 h-[2px] bg-neo-white"></div>
   </Transition>
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