<script context='module'>
    export async function load({ fetch, params }) {
        // await new Promise(resolve => setTimeout(resolve, 1000))
        // const id = params.id
        const res = await fetch (`/api/blog/${params.id}.json`)
        const {blog} = await res.json()

        if (res.ok) {
        return {
            props: {
                blog
                }
            }
        }

        return {
            status: 404
        }
    }

</script>

<script>
    export let blog
</script>

<svelte:head>
    <title>{ blog.title }</title>
</svelte:head>


<div class='blog-detail'>
    <h2>{ blog.title }</h2>
    <p>{ blog.body }</p>
</div>


<style> 
    .blog-detail {
        text-align: center;
        display: block;
        margin: 20px auto;
        font-family: Jetbrains Mono;
    }
</style>