<script setup>
import { ref } from "vue";
import "./assets/main.css";
import google from "@/assets/google.svg";
import github from "@/assets/github.svg";
import emailIcon from "@/assets/email.svg";
import passwordIcon from "@/assets/password.svg";
import unlockedIcon from "@/assets/unlocked.svg";
import closedIcon from "@/assets/closed.svg";
import openIcon from "@/assets/open.svg";

const showPassword = ref(false);

const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value;
};
</script>

<template>
  <div
    class="flex flex-col items-center justify-center min-h-screen text-center"
  >
    <div
      class="flex flex-col items-center gap-6 justify-center text-center shadow-[0_4px_12px_0px_rgba(0,0,0,0.1)] p-16 rounded-2xl"
    >
      <h2 class="text-3xl font-bold">Auth</h2>
      <p class="text-[#828282] text-xs">Lorem ipsum dolor sit amet.</p>
      <form class="flex flex-col items-center gap-6 justify-center">
        <div class="relative w-full">
          <input
            placeholder="Email"
            type="email"
            class="border border-[#BDBDBD] pl-10 pr-4 py-2 rounded-md w-full"
          />
          <div
            class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
          >
            <img :src="emailIcon" alt="" class="w-4" />
          </div>
        </div>
        <div class="relative w-full">
          <input
            :type="showPassword ? 'text' : 'password'"
            placeholder="Password"
            class="border border-[#BDBDBD] pl-10 pr-10 py-2 rounded-md w-full"
          />
          <div
            class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
          >
            <img
              :src="showPassword ? unlockedIcon : passwordIcon"
              alt=""
              class="w-4"
            />
          </div>
          <div
            class="absolute inset-y-0 right-0 pr-3 flex items-center cursor-pointer"
            @click="togglePasswordVisibility"
          >
            <img
              :src="showPassword ? openIcon : closedIcon"
              alt=""
              class="w-4"
            />
          </div>
        </div>
        <button class="bg-[#2F80ED] rounded-xl px-4 py-2 text-white w-full">
          Start now
        </button>
      </form>
      <p class="text-[#828282] text-xs">
        or continue with these social profile
      </p>
      <div class="flex gap-4">
        <a href="">
          <img
            :src="google"
            alt=""
            class="border w-8 border-[#BDBDBD] rounded-full p-2 transition duration-300 ease-in-out hover:scale-150 hover:text-white"
          />
        </a>
        <a href="">
          <img
            :src="github"
            alt=""
            class="border w-8 border-[#BDBDBD] rounded-full p-2 transition duration-300 ease-in-out hover:scale-150 hover:text-white"
          />
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
