<script>
  import { fade } from "svelte/transition";
  const toLangTitle = (lang) => {
    let str = lang.replace(".png", "");
    return (
      "written in " + str.charAt(0).toUpperCase() + str.slice(1).toLowerCase()
    );
  };

  let projects = [
    {
      title: "Fetch master 6000",
      desc: "Simple Dilbert themed system information fetching tool for Linux and BSD based systems.",
      lang: "perl.png",
      url: "https://github.com/anhsirk0/fetch-master-6000",
    },
    {
      title: "Arranger",
      desc: "Simple and capable Files and Directory arranger/cleaner.",
      lang: "perl.png",
      url: "https://github.com/anhsirk0/file-arranger",
    },
    {
      title: "Slider-login-signup",
      desc: "Login/Signup design with a slider animation made with tailwindcss and nextjs.",
      lang: "js.png",
      url: "https://github.com/anhsirk0/slider-login-signup",
    },
    {
      title: "Quote-uploader",
      desc: "Create slideshow of images from brainyquote and upload to dailymotion.",
      lang: "bash.png",
      url: "https://github.com/anhsirk0/quote-uploader",
    },
    {
      title: "News-cli",
      desc: "News and article viewing utility using New-York times API.",
      lang: "rust.png",
      url: "https://github.com/anhsirk0/news-cli",
    },
    {
      title: "Photomosaic",
      desc: "Python program to create photomosaics (image made of smaller images as mosaic tiles).",
      lang: "python.png",
      url: "https://github.com/anhsirk0/photomosaic-python",
    },
    {
      title: "Kakoune-themes",
      desc: "Color schemes for kakoune , extra syntax highlighting and my config.",
      lang: "kakounescript",
      url: "https://github.com/anhsirk0/kakoune-themes",
    },
    {
      title: "Django projects",
      desc: "Some Django projects for CS50 submissions.",
      lang: "python.png",
      url: "https://github.com/anhsirk0/django-projects",
    },
    {
      title: "Pygames",
      desc: "Some simple 2D games made with Pygame.",
      lang: "python.png",
      url: "https://github.com/anhsirk0/pygames",
    },
  ];
</script>

<svelte:head>
  <title>Projects • Anhsirk0</title>
</svelte:head>

<div
  in:fade
  class="grid grid-cols-6 gap-4 lg:gap-8 w-[86vw] lg:w-[66vw] xl:w-[70vw] mb-8 lg:my-0 lg:p-8 mt-4"
>
  {#each projects as project (project.title)}
    <div
      class="card bg-base-200 hover:ring-2 hover:ring-primary col-span-6 md:col-span-3 2xl:col-span-2"
    >
      <div class="card-body p-4 lg:p-8">
        <div class="flex flex-row gap-4 mb-1 xl:mb-2">
          <p class="text-lg md:text-2xl 2xl:text-3xl font-bold">
            {project.title}
          </p>
          {#if project.lang.includes("png")}
            <img
              class="h-10 border-1 border-neutral-focus p-1 rounded-lg"
              title={toLangTitle(project.lang)}
              alt={project.title}
              src={"/" + project.lang}
            />
          {:else}
            <span
              title={toLangTitle(project.lang)}
              class="h-10 w-10 border-1 border-neutral-focus text-2xl text-secondary-content rounded-lg flex items-center justify-center"
              >{project.lang[0]}</span
            >
          {/if}
        </div>
        <p class="lg:text-xl">
          {project.desc}
        </p>
        <div class="ml-auto">
          <a href={project.url} target="_blank">
            <img
              class="h-12 rounded-lg bg-neutral-focus p-2"
              alt="View on github"
              src="/github.png"
            />
          </a>
        </div>
      </div>
    </div>
  {/each}
</div>
