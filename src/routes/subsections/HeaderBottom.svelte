<script>
  import { horizontalSectionMarginClass } from "$lib/portfolio-details";

  let showMenu = false; // To toggle the visibility of the vertical menu

  const links = [
    { title: 'About', link: '#about' },
    { title: 'Services', link: '#services' },
    { title: 'Blogs', link: '#blogs' },
    { title: 'Testimonials', link: '#testimonials' },
    { title: 'Experience', link: '#experience' },
  ];

  const contactButtonDetails = {
    title: 'Contact Us',
    link: '#contact-us',
  };
</script>

<div class="flex flex-row justify-between items-center rounded-md my-4 {horizontalSectionMarginClass}">
  <!-- Logo -->
  <img src="header/nutritionist-logo-and-text.png" class="lg:w-[200px] lg:h-[50px] w-[140px] h-[35px]" alt="">

  <!-- Toggle Button (Shown only on smaller screens) -->
  <img src="header/open-menu-icon.png" class="block lg:hidden" alt="" on:click={() => (showMenu = !showMenu)}>

  <!-- Navigation Links (Horizontal on larger screens, hidden on smaller screens) -->
  <div class="hidden lg:flex flex-row lg:gap-8 gap-4 items-center">
    <div class="flex flex-row gap-5">
      {#each links as linkData}
        <a href={linkData.link} class="font-semibold text-[18px] text-white hover:text-[#CBEA7B]">{linkData.title}</a>
      {/each}
    </div>
    <a href={contactButtonDetails.link}>
      <button class="bg-[#CBEA7B] rounded-md px-4 py-3 font-semibold text-[18px]">
        {contactButtonDetails.title}
      </button>
    </a>
  </div>
</div>

<!-- Vertical Menu (Shown only on smaller screens when toggled) -->
<div 
  class="lg:hidden flex flex-col gap-4 mt-4 p-4 bg-[#1A3129] text-white rounded-md transition-all duration-300 ease-in-out"
  class:hidden={!showMenu}
>
  {#each links as linkData}
    <a href={linkData.link} class="font-semibold text-[16px] text-center text-white hover:text-[#CBEA7B]">{linkData.title}</a>
  {/each}
  <a href={contactButtonDetails.link} class="flex justify-center">
    <button class="bg-[#CBEA7B] rounded-md px-4 py-3 mx-auto text-black font-semibold text-[16px]">
      {contactButtonDetails.title}
    </button>
  </a>
</div>
