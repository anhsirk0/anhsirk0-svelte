<script>
  export let title = "This is card";
  export let Icon = "";
  export let url = "";
</script>

<a href={url} class="card bg-base-200 hover:bg-primary-focus">
  <div
    class="card-body flex flex-row md:flex-col gap-2 md:gap-4 items-center md:items-start p-6 md:p-8"
  >
    <p class="text-xl md:text-4xl font-semibold">{title}</p>
    <svelte:component this={Icon} classes="h-6 w-6 md:h-10 md:w-10 ml-auto" />
  </div>
</a>
