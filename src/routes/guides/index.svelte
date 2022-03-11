<!--script to fetch data-->
<script context="module">
    export async function load({ fetch }) {
        const res = await fetch('http://jsonplaceholder.typicode.com/posts')
        const guides = await res.json()
        console.log(guides)

        if (res.ok) {
            return {
                props: {
                    guides
                }
            }
        }

        return {
            status: res.status,
            error: new Error('Could not fetch the guides')
        }
    }
</script>

<!-- script for scripting-->
<script>
    export let guides
</script>

<!-- components -->
<div class="guides">
    <ul>
        {#each guides as guide}
            <li>
                <a sveltekit:prefetch href={`/guides/${guide.id}`}>{guide.title}</a>
            </li>
        {/each}
    </ul>
</div>

<!-- styles -->
<style>
    .guides {
        margin-top: 20px;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    a {
        display: inline-block;
        margin-top: 10px;
        padding: 10px;
        border: 1px dotted rgba(255, 255, 255, 0.2);
    }
</style>