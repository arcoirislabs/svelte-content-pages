<script>
    
    export let page;
    export let fallbackSelection;
    let pagesList;
    
    import {onMount} from "svelte";
    onMount(function (params) {
        
        for (let index = 0; index < pagesList.children.length; index++) {
            const element = pagesList.children[index];
            console.log(index , page , fallbackSelection);
            if (index == 0 && page == null && fallbackSelection !== undefined) {
                
                element.style.display = "block";
            }else{
                element.style.display = "none";
            }
        }
        showPage(page);
    });
    function showPage(page) {
        
        if (page != null && pagesList !=undefined) {
            for (let index = 0; index < pagesList.children.length; index++) {
                const element = pagesList.children[index];
                element.style.display = "none";
            };
            //console.log(pagesList.querySelector('.page[page='+page+']'))
            pagesList.querySelector('[page='+page+']').style.display = "block";
        }else{
            
        }
    }
    $: showPage(page)
    //page = capitalize(page);
</script>


<div class="pages" bind:this="{pagesList}" current-page={page} style="--current-page:{page}">
    <slot></slot>
</div>

