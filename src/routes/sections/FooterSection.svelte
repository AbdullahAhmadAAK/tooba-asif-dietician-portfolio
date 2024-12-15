<script>
  import {
    horizontalSectionMarginClass,
    horizontalSectionPaddingClass,
  } from "$lib/portfolio-details";

  import SocialIcons from '@rodneylab/svelte-social-icons';

  const footerLinks = [
    { name: "Home", link: "#home" },
    { name: "Services", link: "#services" },
    { name: "Testimonials", link: "#testimonials" },
    { name: "Experience", link: "#experience" },
    { name: "Education", link: "#education" },
    { name: "Contact", link: "#contact" },
  ];
</script>

<footer class="bg-[#1A3129] mt-10 md:px-40 px-4">
  <nav>
    <!-- Top section -->
    <div class="flex flex-col lg:flex-row flex-wrap items-center justify-between mx-auto p-4">
      <!-- Logo -->
      <a href="#" class="flex items-center space-x-3 rtl:space-x-reverse mb-4 md:mb-0">
        <img src="footer/tooba-asif-nutrition.png" class="w-10 h-10" alt="Logo" />
        <span
          class="self-center text-2xl font-semibold whitespace-nowrap text-[#ffffff]">
          Nutritionist
        </span>
      </a>

      <div class="w-full md:block md:w-auto" id="navbar-default">
        <ul
          class="flex flex-col md:flex-row items-center space-y-4 md:space-y-0 md:space-x-8 bg-[#1A3129] font-medium p-4 md:p-0 rounded-lg md:rounded-none"
        >
          {#each footerLinks as linkDetails}
            <li>
              <a
                href={linkDetails.link}
                class="font-sans font-semibold text-sm text-[#FFFFFF] hover:text-[#CBEA7B] block py-2 md:py-0"
                aria-current="page">{linkDetails.name}</a>
            </li>
          {/each}
          <!-- Up Arrow -->
          <a
            class="flex justify-center items-center w-12 h-12 hover:cursor-pointer rounded-[73px] bg-[#234338]"
            href="#home"
          >
            <img src="footer/up.png" alt="up" class="w-3 h-4" />
          </a>
        </ul>
      </div>
    </div>
  </nav>

  <!-- Bottom Section -->
  <div class="px-4 md:px-16 py-4 flex flex-col md:flex-row md:justify-between items-center bg-[#234338] gap-y-4 md:gap-y-0 gap-x-8">
    <!-- Contact Info -->
    <div class="flex flex-col md:flex-row gap-5 items-center md:items-start">
      <!-- Email -->
      <div class="flex items-center gap-2">
        <img src="footer/email.png" alt="email" class="w-5 h-5" />
        <a
          href="mailto:toobaasif167@gmail.com"
          class="font-sans font-medium text-base text-[#FFFFFF] hover:underline"
        >
          toobaasif167@gmail.com
        </a>
      </div>
      <!-- Phone -->
      <div class="flex items-center gap-2">
        <img src="footer/phone.png" alt="phone" class="w-5 h-5" />
        <a
          href="tel:+923028931717"
          class="font-sans font-medium text-base text-[#FFFFFF] hover:underline"
        >
          +92 302 8931 717
        </a>
      </div>
      <!-- Location -->
      <div class="flex items-center gap-2">
        <img src="footer/location.png" alt="location" class="w-5 h-5" />
        <a
          href="https://www.google.com/maps?q=Islamabad,+Pakistan"
          target="_blank"
          rel="noopener noreferrer"
          class="font-sans font-medium text-base text-[#FFFFFF] hover:underline"
        >
        Islamabad, Pakistan
        </a>
      </div>
    </div>

    <!-- Social Media Icons -->
    <div class="flex justify-center md:justify-end w-full md:w-auto gap-4">
      <!-- LinkedIn -->
      <a
        href="https://www.linkedin.com/in/tooba-asif-4708a72b5/"
        target="_blank"
        rel="noopener noreferrer"
        class="text-[#FFFFFF] hover:text-[#0077B5]"
      >
        <SocialIcons network="linkedin" alt="" bgColor="#f5fdf3" fgColor="#0077B5" />

      </a>
      <!-- Instagram -->
      <a
        href="https://www.instagram.com/toobanutrition.co/"
        target="_blank"
        rel="noopener noreferrer"
        class="text-[#FFFFFF] hover:text-[#E1306C]"
      >
        <SocialIcons network="instagram" alt="" bgColor="#f5fdf3" fgColor="#C13584" />
      </a>
    </div>
  </div>
</footer>
