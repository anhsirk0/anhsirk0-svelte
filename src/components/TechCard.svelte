<script>
  export let items = [];
  export let title = "";
</script>

<div class="card bg-base-200 hover:ring-2 hover:ring-primary">
  <div class="card-body p-4 lg:p-8">
    <p class="text-xl md:text-3xl 2xl:text-4xl mb-3 xl:mb-4 font-bold">
      {title}
    </p>
    <div class="flex flex-wrap gap-4">
      {#each items as item (item.title)}
        <a
          href={item.url}
          target="_blank"
          class="tooltip tooltip-top"
          data-tip={item.title}
        >
          <div
            class="h-20 w-20 md:h-24 md:w-24 flex items-center border-1 border-neutral-focus rounded-xl p-1 md:p-2"
          >
            <img alt={item.title} src={"/" + item.img} />
          </div>
        </a>
      {/each}
    </div>
  </div>
</div>
