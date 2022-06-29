<script>
    const title = 'About Us'
</script>

<svelte:head>
    <title>{title}</title>
</svelte:head>

<div class="about">
    <h2>{title}</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil dolor accusantium repudiandae, consequatur autem, perferendis itaque dolorum aliquam molestias tenetur dolorem provident officiis in temporibus? Labore mollitia a ratione cum?</p>
    <a href="/">Back Home</a>
</div>

<style>
    .about{
        text-align: center;
        display: block;
        margin: 20px auto;
        font-family: Jetbrains Mono;
    }

    a {
        text-decoration: none;
    }
</style>