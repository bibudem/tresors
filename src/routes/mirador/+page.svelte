<svelte:head>
    <script src="https://unpkg.com/mirador@latest/dist/mirador.min.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
</svelte:head>

<h1>Mirador de Martin</h1>
<p>Un test (2)!</p>
<div id="mirador"></div>
<script>
    import { onMount } from 'svelte';

    onMount(() => {
    // Instantiate Mirador viewer
        const urlParams = new URLSearchParams(window.location.href);
        const manifestUrl = urlParams.get("iiif-content");
        var miradorInstance = Mirador.viewer({
            id: 'mirador',
            windows: [{
//                manifestId: 'https://bibudem.github.io/tresors-iiif/manifests/50335781.json'
                manifestId: manifestUrl
            }],
            language: 'fr'
        });
    });
</script>

