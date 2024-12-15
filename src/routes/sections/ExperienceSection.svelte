<script>
    import { horizontalSectionMarginClass } from "$lib/portfolio-details";

  const works = [
    {
      image: "experience/dha-logo.png",
      title: "Clinical Dietician",
      icon: "experience/office-logo.png",
      subheading: "Avicenna Clinic",
      icon2: "experience/location-icon.png",
      subheading2: "Onsite",
      button: "Part-time",
      timeline: "Jun. 2024 - Aug. 2024",
    },
    {
      image: "experience/cmh-army-logo.png",
      title: "Dietician Trainee",
      icon: "experience/office-logo.png",
      subheading: "Nelson Medical Complex",
      icon2: "experience/location-icon.png",
      subheading2: "Onsite",
      button: "Internship",
      timeline: "Jul. 2024 - Aug. 2024",
    },
    {
      image: "experience/cmh-army-logo.png",
      title: "Intern Dietician",
      icon: "experience/office-logo.png",
      subheading: "CMH Rawalpindi",
      icon2: "experience/location-icon.png",
      subheading2: "Onsite",
      button: "Internship",
      timeline: "Aug. 2023 - Oct. 2023",
    },
    {
      image: "experience/cmh-army-logo.png",
      title: "Intern Dietician",
      icon: "experience/office-logo.png",
      subheading: "CMH Rawalpindi",
      icon2: "experience/location-icon.png",
      subheading2: "Onsite",
      button: "Internship",
      timeline: "Jul. 2022 - Aug. 2022",
    },
  
  ];
</script>

<h1 class="font-bold md:text-[48px] sm:text-[38px] text-[28px] text-[#262626] mt-20 h-14 text-center" id="experience">
  Work Experience
</h1>

<div class="flex flex-col {horizontalSectionMarginClass} mt-10 gap-y-8 items-center">
  <!-- generates rows -->
  {#each works as work}
    <div class="flex flex-col md:flex-row items-center gap-4 w-full max-w-3xl px-4 py-6 bg-[#F6FBE9] shadow-lg hover:shadow-xl rounded-lg transition-all duration-300">
      <!-- Work Image -->
      <img
        src={work.image}
        alt="placeholder"
        class="w-20 h-20 md:w-[88px] md:h-[88px] rounded-md border-[#CBEA7B] border-2 hover:border-green-500 transition-all duration-300"
      />
      
      <!-- Content Section -->
      <div class="flex flex-1 flex-col">
        <h1 class="text-lg md:text-xl text-center md:text-start font-semibold text-green-700 mb-2">
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
      <div class="flex flex-col items-center md:items-end">
        <button
          class="bg-green-100 text-green-600 text-xs md:text-sm font-semibold inline-block rounded-full py-1 px-4 hover:bg-green-200 transition-all duration-300"
        >
          {work.button}
        </button>
        <p class="text-green-500 text-sm mt-2">{work.timeline}</p>
      </div>
    </div>
    <!-- Divider -->
    <hr class="w-full max-w-3xl border-green-300 border-t-2" />
  {/each}
</div>


