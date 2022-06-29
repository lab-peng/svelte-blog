<script context="module">
    export async function load({ fetch }) {
        const res = await fetch('/api/blogs.json')
        const  { blogs }  = await res.json()
        
        console.log(blogs)
        if (res.ok) {
            return {
                props: {
                    blogs
                },
                // cache: {
                // "maxage": 300, // 5 mins
                // "private": false
                // }
            }
        }

        return {
            status: res.status,
            error: new Error('Fetch Failure')
        }
    }

</script>

<script>
    export let blogs
</script>


<svelte:head>
    <title>All Blogs</title>
</svelte:head>

<div class="all">
    <h2>All Blogs</h2>
    <div class="blog-list">
        {#each blogs as blog }
        <div class="blog-single">
            <a href="{ `/blog/${blog.id}` }"><h4>{blog.title}</h4></a>
            <p>{blog.snippet}</p>
        </div>
        {/each }
    </div>
</div>

<style>
    h2 {
        text-align: center;
    }

    .all{
        display: block;
        margin: 20px auto;
        font-family: Jetbrains Mono;
    }

    .blog-single p {
        font-size: 0.8rem;
    }

    a {
        text-decoration: none;
    }
</style>