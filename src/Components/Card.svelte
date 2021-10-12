<script lang="ts">
    export let title: string;
    export let index: number;
    export let remove: (index: number) => void;
</script>

<body>
    <div class="card">
        <h2 class="title">{title}</h2>
        <button on:click={() => remove(index)}>Done</button>
    </div>
</body>

<style type="text/postcss">
    .card {
        @apply w-full border-2 border-gray-600 grid grid-cols-2 grid-rows-1 p-3 rounded-md my-4;
    }

    .title {
        @apply float-left;
        overflow-wrap: break-word;
        width: 80%;
    }
</style>