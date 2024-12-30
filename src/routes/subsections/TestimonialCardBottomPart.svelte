<script>
  export let testimonial;

  // console.log(
  //   "this is the card in compo:",
  //   testimonial,
  //   testimonial.link,
  //   testimonial.link == undefined,
  //   testimonial.link != undefined,
  // );
</script>

<div
  class="flex items-center gap-3 bg-[#E6F4D7] md:py-8 md:px-5 sm:py-5 sm:px-8 py-5 px-6 rounded-b-2xl transition-colors duration-300 group-hover:bg-[#AEE06C]"
  style="flex: 0 0 auto;"
>
  <img
    src={testimonial.image}
    alt="testimonial"
    class="rounded-lg
            md:min-h-[60px] md:max-h-[60px] md:min-w-[60px] md:max-w-[60px]
            sm:min-h-[50px] sm:max-h-[50px] sm:min-w-[50px] sm:max-w-[50px]
            min-h-[40px] max-h-[40px] min-w-[40px] max-w-[40px]
            group-hover:scale-110 transition-transform duration-300"
  />
  <div class="flex flex-col gap-2">
    {#if testimonial.hasLink}
      <a
        class="font-semibold hover:underline md:text-[18px] text-[16px] text-[#333333] group-hover:text-[#1A1A1A] transition-colors duration-300"
        href={testimonial.link}
        target="_blank"
      >
        {testimonial.name}
      </a>
    {:else}
      <p
        class="font-semibold md:text-[18px] text-[16px] text-[#333333] group-hover:text-[#1A1A1A] transition-colors duration-300"
      >
        {testimonial.name}
      </p>
    {/if}

    <p
      class="font-medium text-[#666666] md:text-[16px] text-[14px] group-hover:text-[#1A1A1A] transition-colors duration-300"
    >
      {testimonial.designation}
    </p>
  </div>
</div>
