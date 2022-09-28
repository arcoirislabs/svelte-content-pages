# svelte-content-pages

[![npm version](https://badge.fury.io/js/svelte-content-pages.svg)](https://badge.fury.io/js/svelte-content-pages)

Svelte Element to do easy Content Switching. The inspiration came from [<iron-pages>](https://www.webcomponents.org/element/@polymer/iron-pages)

## How to use

Here is how you can use

```bash
# install 
npm i svelte-content-pages

```

Copy this in your App.svelte file 

```javascript
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
```

You can use dynamic views using this library, but you may need to set a static Page section