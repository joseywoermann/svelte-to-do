<script lang="ts">
    import Card from "../Components/Card.svelte";
    import Add from "../Components/Add.svelte";

    let tasks: string[] = [];
    let title: string = "";

    const addTask = (title: string) => {
        tasks = [...tasks, title];
        title = "";
    };

    const removeTask = (index: number) => {
        tasks.splice(index, 1)
        tasks = tasks
    }
</script>


<body>
    <Add title={title} add={addTask}/>
    
    {#each tasks as task, index}
        <Card title={task} index={index} remove={removeTask}/>
    {/each}
</body>