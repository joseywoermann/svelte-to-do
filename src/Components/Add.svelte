<script lang="ts">
    export let title: string;
    export let add: (title: string) => void;

    const placeholders: string[] = [
        "Do something",
        "Finish that side project",
        "Write a blog post",
        "Go outside"
    ];
    const placeholder = placeholders[Math.floor(Math.random() * placeholders.length)];
</script>


<body>
    <div class="add-form">
        <input class="add-bar w-4/5" type="text" placeholder={placeholder} bind:value={title}/>
        <button class="submit w-1/5" on:click={() => {
            if (title === "") return;
            add(title);
            title = "";
        }}>Add</button>
    </div>
</body>

<style type="text/postcss">
    .add-form {
        @apply mb-4;
    }

    .add-bar {
        @apply rounded-md p-3 text-lg border-2 border-gray-600 float-left;
    }

    .submit {
        @apply float-right text-4xl align-middle;
    }
</style>