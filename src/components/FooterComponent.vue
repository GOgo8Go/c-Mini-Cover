<template>
  <footer class="sm:mt-12 mb-2 text-center text-xs sm:text-sm">
    <div class="flex flex-wrap justify-center gap-x-2 gap-y-1">
 
    </div>
    <div class="mt-2 space-x-2">
      <span>© 2024</span>
      <a href="https://bsgun.cn" 
         target="_blank"
         class="font-bold text-green-600 hover:text-gray-600 transition-colors">图片</a>
      <a v-if="icpNumber" 
         href=" " 
         target="_blank"
         class="font-bold text-green-600 hover:text-gray-600 transition-colors">{{ icpNumber }}</a>
      <button class="text-pink-500 font-bold" @click="toggleTips"> </button>
    </div>
    
    <!-- 小提示弹窗 -->
    <div class="fixed top-0 left-1/2 w-[90%] max-w-[600px] max-h-[82px] p-[10px] mt-[10px] bg-white text-[#333] rounded-[10px] shadow-[0_4px_8px_#0000001a] z-100 flex flex-col justify-center items-center text-center overflow-hidden transition-all duration-300 ease-in-out"
         :style="{
           opacity: showTipsPopup ? 1 : 0,
           visibility: showTipsPopup ? 'visible' : 'hidden',
           transform: `translate(-50%) translateY(${showTipsPopup ? '0' : '-20px'})`
         }"
    >
      <div class="flex flex-col text-base items-center justify-center">
        
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      showTipsPopup: false,
      icpNumber: import.meta.env.VITE_APP_ICP_NUMBER
    };
  },
  methods: {
    toggleTips() {
      this.showTipsPopup = !this.showTipsPopup;
      if (this.showTipsPopup) {
        setTimeout(() => {
          this.showTipsPopup = false;
        }, 3000);
      }
    }
  }
};
</script>
