<script setup>
useHead({
  title: "Thanadon Trakanpong",
  htmlAttrs: {
    class: 'scroll-smooth'
  },
  bodyAttrs: {
    class:
      "bg-slate-900 leading-relaxed text-slate-400 antialiased selection:bg-violet-800/20 selection:text-violet-200",
  },
});
const { x, y } = useMouse();
const { width } = useWindowSize();
</script>

<template>
  <div class="relative overflow-clip font-sans">
    <!-- content -->
    <div class="mx-auto min-h-screen max-w-screen-xl">
      <NuxtPage />
    </div>
    <!-- cursor animation -->
    <div
      class="fixed lg:absolute -z-10 -translate-x-1/2 -translate-y-1/2 transition duration-300 w-[50rem] h-[50rem] rounded-full pointer-events-none blur-3xl"
      :style="{
        left: `${width >= 1024 ? x : 0}px`,
        top: `${width >= 1024 ? y : 0}px`,
        background: `radial-gradient(
          #1d4fd820,
          transparent 80%
        )`,
        // background: 'red'
      }"
    ></div>
  </div>
</template>
