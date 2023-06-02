<script >
    import { AppRail,AppRailTile } from '@skeletonlabs/skeleton';
    import { zip } from 'lodash';

    let tile_num='default';

    const routes = [
        'guiding','camera','weather','fix','arts','stats','tools'
    ]

    const names = [
        'Guiding',"Camera","Weather","AstroFix Studio","AstroArts Studio","Hardware Stats","Tools"
    ]

    const imagepaths = routes.map(n=>`/src/logos/dashboard/${n}/${n}-color.svg`)

    const indexs     = imagepaths.map((n,i)=>i)

    const sum        = zip(routes,  names, imagepaths,indexs);
    
</script>

<AppRail>
    {#each sum as [route,  name, imagepath,i]}
        <AppRailTile bind:group={tile_num} name="tile-{i+1}" value={{i}} class="mb-4">
            <a href="/{route}" class="flex-col justify-center items-center">
                <object data="{imagepath}"  class="ml-4" title="{route}" type="image/svg+xml" width="50px"></object>
                <strong class="text-center">{name}</strong>
            </a>
        </AppRailTile>
    {/each}
</AppRail>
