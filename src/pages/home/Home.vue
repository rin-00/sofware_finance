<script lang="ts" setup>
  import { GithubFilled } from '@ant-design/icons-vue';
  import { useRouter } from 'vue-router';

  const router = useRouter();
  function signIn() {
    router.push('/login');
  }
</script>
<template>
  <div class="home pt-[140px] text-center">
    <div class="tracking-wide slogan text-[84px] font-extralight">
      <span class="font-semibold">Keep.</span> Going.
    </div>
    <p class="text-subtext text-[28px] font-light tracking-wide">
      <!-- The most-loved Vue3 Framework in github.com and gitee.com -->
    </p>
    <button
      @click="signIn"
      class="bg-primary-600 hover:bg-primary-700 cursor-pointer mt-lg shadow border-0 outline-none text-xl px-[64px] py-lg rounded-sm"
    >
      Start
      <br />
      <div class="text-base text-subtext"><GithubFilled /> @vvvviolet</div>
    </button>
    <br />
    <div class="inline-block text-blue-200 text-xl mr-lg">Powered by:</div>
    <div class="powered-by-list inline-flex mt-xl text-subtext">
      <a href="https://www.antdv.com/" target="_blank" class="powered-by text-subtext hover:text-text cursor-pointer">
        <img class="w-6" src="@/assets/logo/antdv.svg" />
        antd design vue
      </a>
      <a
        href="https://tailwindcss.com/"
        target="_blank"
        class="powered-by text-subtext mx-md hover:text-text cursor-pointer"
      >
        <img class="w-6" src="@/assets/logo/tailwindcss.svg" />
        tailwindcss
      </a>
      <a href="http://www.vitejs.net/" target="_blank" class="powered-by text-subtext hover:text-text cursor-pointer">
        <img class="w-5" src="@/assets/vite.svg" />
        vitejs
      </a>
    </div>
  </div>
</template>
<style scoped lang="less"></style>
