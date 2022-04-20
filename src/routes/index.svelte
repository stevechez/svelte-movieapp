<script context="module">
    export async function load({ fetch }) {
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=df131a256cf78ed76b7926454a2b1cb5`)
        const data = await res.json();
        if (res.ok) {
            return {
                props: { popular: data.results }
            }
        }
    }
</script>

<script>
    import PopularMovies from "../components/PopularMovies.svelte";
    export let popular;
</script>

<section>
    <PopularMovies {popular} />
</section>