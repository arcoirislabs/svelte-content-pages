<script>
    import {
        Page, 
        Pages
    } from "svelte-content-pages";
    var page = "";
    let fallbackSelectionView = "home";
</script>
<Pages page={page} fallbackSelection="{fallbackSelectionView}">
    <Page page="home">
        Home Page
    </Page>
    <Page page="about">
        About Page
    </Page>
</Pages>