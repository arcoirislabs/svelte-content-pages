<script>
    
    export let page;
    export let fallbackSelection;
    let pagesList;
    
    import {onMount} from "svelte";
    onMount(function () {
        
        for (let index = 0; index < pagesList.children.length; index++) {
            const element = pagesList.children[index];
            if (index == 0 && page == null && page.length == 0 && fallbackSelection !== undefined) {
                element.style.display = "block";
            }else{
                element.style.display = "none";
            }
        }
        showPage(page);
    });
    function showPage(page) {
        
        if (page != null && page.length > 0 && pagesList !=undefined) {
            for (let index = 0; index < pagesList.children.length; index++) {
                const element = pagesList.children[index];
                element.style.display = "none";
            };
            
            pagesList.querySelector('[page='+page+']').style.display = "block";
        }else{
            
        }
    }
    $: showPage(page)
    
</script>

<div class="pages" bind:this="{pagesList}" current-page={page} style="--current-page:{page}">
    <slot></slot>
</div>

