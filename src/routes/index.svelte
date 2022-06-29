<script>
    let title = 'Svelte Blog'

    const toggleTitle = () =>  {
        title = title === 'Svelte Blog'? 'Ninja Blog': 'Svelte Blog'
        // if (title === 'Svelte Blog'){
        //     title = 'Ninja Blog'
        // } else {
        //     title = 'Svelte Blog'
        // }
    }
</script>
<svelte:head>
    <title>{title}</title>
</svelte:head>
<div class="index">
    <h2>{ title }</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fugit labore obcaecati, inventore est, fuga delectus adipisci sint dolor distinctio quia magni soluta laborum dolore amet voluptatibus repudiandae! Sapiente, consectetur debitis?</p>
    <button on:click={toggleTitle}>Change Title</button>
</div>

<style>
    .index{
        text-align: center;
        display: block;
        margin: 20px auto;
        font-family: Jetbrains Mono;
    }
</style>