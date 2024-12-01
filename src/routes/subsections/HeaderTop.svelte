<script>
  import {
    headerSubColor,
    horizontalSectionPaddingClass,
    horizontalSectionMarginClass,
  } from "$lib/portfolio-details";
  import { onMount } from "svelte";

  let isLaptopView = false;

  const checkViewport = () => {
    isLaptopView = window.innerWidth > 768; // Adjust breakpoint as needed
  };

  onMount(() => {
    checkViewport(); // Check the initial width
    window.addEventListener("resize", checkViewport); // Listen for changes
    return () => window.removeEventListener("resize", checkViewport); // Cleanup
  });
</script>

<div
  class="flex flex-row justify-center md:justify-between rounded-md {horizontalSectionPaddingClass} my-4 {horizontalSectionMarginClass} bg-[#234338]"
>
  {#if isLaptopView}
    <img src="header/left-squiggly-vector.png" alt="" />
  {/if}

  <div class="flex justify-center gap-6 items-center">
    <div
      class="flex flex-row items-center gap-2 font-medium md:text-[18px] text-[14px] text-white"
    >
      <img src="header/ball.png" class="h-5 w-5" alt="" />
      <span class="text-center"
        >Join Our Personalized Nutrition Demo For Free</span
      >
    </div>

    <img src="header/right-arrow.png" alt="" />
  </div>
  {#if isLaptopView}
    <img src="header/right-squiggly-vector.png" alt="" />
  {/if}
</div>
