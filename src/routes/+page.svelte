<script lang="ts">
    import {Page, Pages} from "$lib";
    var page = "";
    let fallbackSelectionView = "home";
</script>
<style>
   .code{
        width: 30%;
   }
</style>
<h1>
    Svelte based Content Switcher
</h1>
<p>
    Here we are switching views using a string and hiding other views. You can load components statically or dynamically, provided you declare a unique Page element for that dynamic view.
</p>
<a href="https://github.com/arcoirislabs/svelte-pages/examples">See Example</a>
<div>
    <img class="code" src="code.png" alt="" srcset="">
</div>
<div>
    <h4>
        Actual Code
    </h4>
</div>
<div>
    <button on:click="{()=>{page = "home"}}">Set Home page</button>
    <button on:click="{()=>{page = "about"}}">Set About page</button>
</div>
<div>
    <Pages page={page} fallbackSelection="{fallbackSelectionView}">
        <Page page="home">
            Home Page
        </Page>
        <Page page="about">
            About Page
        </Page>
    </Pages>
</div>
