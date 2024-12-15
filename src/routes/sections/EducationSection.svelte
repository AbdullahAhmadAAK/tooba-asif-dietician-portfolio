<script>
      import { horizontalSectionMarginClass } from "$lib/portfolio-details";


  const works = [
    {
      image: "education/university-of-lahore-logo.png",
      title: "Bachelor of Science - Dietitics and Nutritional Sciences",
      icon: "experience/office-logo.png",
      subheading: "University of Lahore",
      icon2: "experience/location-icon.png",
      subheading2: "Rawalpindi, Pakistan",
      button: "Onsite",
      timeline: "Aug. 2019 - Jul. 2024",
    }
  ];
</script>

<h1 class="font-bold md:text-[48px] sm:text-[38px] text-[28px] text-[#262626] mt-20 h-14 text-center">
  Education
</h1>

<div class="flex flex-col {horizontalSectionMarginClass} mt-10 gap-y-8 items-center">
  <!-- generates rows -->
  {#each works as work}
    <div class="flex flex-col md:flex-row items-start md:items-center gap-4 w-full max-w-3xl px-4 py-6 bg-[#F6FBE9] shadow-lg hover:shadow-xl rounded-lg transition-all duration-300">
      <!-- Work Image -->
      <img
        src={work.image}
        alt="placeholder"
        class="w-20 h-20 md:w-[88px] md:h-[88px] rounded-md border-[#CBEA7B] border-2 hover:border-green-500 transition-all duration-300"
      />
      
      <!-- Content Section -->
      <div class="flex flex-1 flex-col">
        <h1 class="text-lg md:text-xl font-semibold text-green-700 mb-2">
          {work.title}
        </h1>
        <div class="flex flex-wrap items-center gap-4">
          <div class="flex items-center gap-2">
            <img
              src={work.icon}
              alt="icon"
              class="w-8 h-8 md:w-10 md:h-10"
            />
            <p class="text-green-600 text-xs lg:text-base">{work.subheading}</p>
          </div>
          <div class="flex items-center gap-2">
            <img
              src={work.icon2}
              alt="icon2"
              class="w-6 h-8"
            />
            <p class="text-green-600 text-xs lg:text-base">{work.subheading2}</p>
          </div>
        </div>
      </div>
      
      <!-- Actions Section -->
      <div class="flex flex-col items-start md:items-end">
        <button
          class="bg-green-100 text-green-600 text-xs md:text-sm font-semibold inline-block rounded-full py-1 px-4 hover:bg-green-200 transition-all duration-300"
        >
          {work.button}
        </button>
        <p class="text-green-500 text-sm mt-2">{work.timeline}</p>
      </div>
    </div>
  {/each}
</div>
