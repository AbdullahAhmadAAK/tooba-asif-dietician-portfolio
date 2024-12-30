<script>
  import TestimonialCardBottomPart from "../subsections/TestimonialCardBottomPart.svelte";
  import { horizontalSectionMarginClass } from "$lib/portfolio-details";
  import { onMount } from "svelte";

  const testimonials = [
    {
      text: "...she helped me last time too, to lost weight and it actually worked, so I have again asked her to make it for me. Because I feel so comfortable telling her anyyything and she understand everything and she is so polite and so so good at her work 🤩😍",
      name: "Manahel Asif Shaykh",
      designation: "Influencer",
      image: "testimonials/animated-woman.jpg",
      hasLink: false,
    },
    {
      text: "Her expertise and personalized approach have made a significant impact on my health and well-being. She truly listens and tailors advice to suit my needs. I highly recommend her to anyone seeking reliable and thoughtful nutrition support.",
      name: "Abdullah Ahmad",
      designation: "Software Engineer",
      image: "testimonials/animated-man.jpeg",
      link: "https://www.linkedin.com/in/abdullah-ahmad-aak/",
      hasLink: true,
    },
    {
      text: "I have lost 2 kgs and it's only been one and a half week! The meals are so fun to make and I am enjoying following my diet plan. Definitely signing up for more!",
      name: "Rimsha Imran",
      designation: "Clinical Psychologist and NLP Coach",
      image: "testimonials/animated-woman.jpg",
      hasLink: false,
    },

    {
      text: "My doctor gave me a new medicine for my diabetes but my fasting sugar levels would still remain above 120mg/dl. It is the first time in so long that my fasting blood sugar was 109mg/dl after beginning working with Dn. Tooba. Now I'm even more determined to continue my plan.",
      name: "Saba Aamir",
      designation: "Homemaker",
      image: "testimonials/animated-woman.jpg",
      hasLink: false,
    },

    {
      text: "I recently started using Happy Gut Herbal Powder and I genuinely feel lighter and less bloated than usual and I love it!",
      name: "Nosheen Usman",
      designation: "Coordinator Montessori HSGTR",
      image: "testimonials/animated-woman.jpg",
      hasLink: false,
    },

    {
      text: "I mainly wanted to lose weight because it was affecting my everyday life but Dn. Tooba introduced me to nutraceuticals in my plan that even my BP is lower than usual! I still have a long way to go but I'm motivated.",
      name: "Mahwish",
      designation: "Homemaker",
      image: "testimonials/animated-woman.jpg",
      hasLink: false,
    },

    {
      text: "I followed Dn. Tooba's plan for a month and my belly fat got reduced by one belt hole! I feel great.",
      name: "Kashif Abbasi",
      designation: "Pakistan Army Brigadier (retired)",
      image: "testimonials/animated-man.jpeg",
      hasLink: false,
    },
  ];

  let currentIndex = 0;

  let isMounted = false;
  let testimonialsToShow = 3; // Default to desktop count

  function goLeft() {
    if (currentIndex > 0) {
      currentIndex = currentIndex - testimonialsToShow;
    }
  }

  function goRight() {
    if (currentIndex < testimonials.length - 1) {
      currentIndex = (currentIndex + testimonialsToShow) % testimonials.length;
    }
  }

  // Adjust testimonialsToShow on the client
  onMount(() => {
    const updateTestimonialsToShow = () => {
      let newTestimonialsToShow = 0;

      if (window.outerWidth > 1200) {
        newTestimonialsToShow = 3;
      } else if (window.outerWidth > 1024) {
        newTestimonialsToShow = 2;
      } else if (window.outerWidth > 640) {
        newTestimonialsToShow = 1;
      } else if (window.outerWidth <= 640) {
        newTestimonialsToShow = 1;
      }

      testimonialsToShow = newTestimonialsToShow;
      // testimonialsToShow = window.outerWidth <= 1200 ? 1 : 3;
    };

    updateTestimonialsToShow(); // Set initial value
    isMounted = true;

    window.addEventListener("resize", updateTestimonialsToShow);

    // Cleanup the event listener on component destroy
    return () => {
      window.removeEventListener("resize", updateTestimonialsToShow);
    };
  });
</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css"
  />
  <script
    src="https://kit.fontawesome.com/a076d05399.js"
    crossorigin="anonymous"
  ></script>
</svelte:head>

<div id="testimonials-section">
  <div
    class="flex flex-col gap-3 md:mt-32 sm:mt-[100px] mt-12"
    id="testimonials"
  >
    <h4
      class="text-white text-center md:text-[48px] sm:text-[38px] text-[28px] font-bold"
    >
      Our Testimonials
    </h4>

    <p
      class="text-white text-center md:text-[18px] sm:text-[16px] text-[14px] font-medium w-[80%] mx-auto"
    >
      Our satisfied clients share their success stories and experiences on their
      journey to better health and well-being.
    </p>
  </div>

  {#if isMounted}
    <div
      class="flex flex-row justify-center md:mt-20 mt-12 gap-x-8 {horizontalSectionMarginClass}"
    >
      {#each testimonials.slice(currentIndex, currentIndex + testimonialsToShow) as testimonial}
        <div
          class="flex min-h-[550px] flex-col rounded-2xl overflow-hidden group transition transform hover:scale-105 hover:shadow-lg"
          style="flex: 1 1 calc(80% - 2rem); max-width: calc(80% - 2rem);"
        >
          <!-- Top Section -->
          <div
            class="flex flex-col flex-1 md:gap-[50px] gap-10 bg-[#FAFDF5] md:p-11 sm:p-8 p-6 rounded-t-2xl transition-colors duration-300 group-hover:bg-[#D6F5A1]"
          >
            <img
              src="testimonials/quote.png"
              alt="quote icon"
              class="md:w-10 md:h-10 w-8 h-8 group-hover:scale-110 transition-transform duration-300"
            />
            <p
              class="font-medium md:text-[18px] sm:text-[16px] text-[14px] text-[#444444] group-hover:text-[#1F1F1F] transition-colors duration-300"
            >
              {testimonial.text}
            </p>
          </div>
          <!-- Bottom Section -->
          <TestimonialCardBottomPart {testimonial} />
        </div>
      {/each}
    </div>
  {/if}

  <div class="flex flex-row mt-10 pb-4 gap-x-4 items-center justify-center">
    <button
      on:click={goLeft}
      class="flex justify-center items-center text-[40px]"
      aria-label="left-arrow-button"
    >
      <img src="left-arrow-svgrepo-com.svg" alt="" class="w-8 h-8" />
    </button>

    <div class="flex gap-2 items-end">
      {#each Array(Math.ceil(testimonials.length / testimonialsToShow)) as _, i}
        <span
          class="md:w-2.5 md:h-2.5 w-2 h-2 rounded-full inline-block"
          style="background-color: {i ===
          Math.floor(currentIndex / testimonialsToShow)
            ? '#356554'
            : '#E5F5BD'}"
        ></span>
      {/each}
    </div>

    <button
      on:click={goRight}
      class="flex justify-center items-center text-[40px]"
      aria-label="right-arrow-button"
    >
      <img src="right-arrow-svgrepo-com.svg" alt="" class="w-8 h-8" />
    </button>
  </div>
</div>

<style>
  .mi {
    font-size: 1.5rem;
  }

  @media (min-width: 640px) {
    .mi {
      font-size: 2rem;
    }
  }

  #testimonials-section {
    background-image: url("experience/tooba-testimonials.png");
    background-size: cover; /* Ensures the image fills the width or height */
    background-repeat: no-repeat; /* Prevents the image from repeating */
    background-position: top center; /* Aligns the image to the top */
    background-color: rgba(
      0,
      0,
      0,
      0.5
    ); /* Adds a dark overlay (adjust opacity as needed) */
    background-blend-mode: darken; /* Blends the dark color with the image */
  }
</style>
