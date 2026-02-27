<script>
    // COMPONENTS
    import { onMount } from 'svelte';
    import { writable } from 'svelte/store';
    import Checklist from '$components/Checklist.svelte';
    import data from '$data/data.js';


    async function clearLocalStorage() {
        console.log('APP INIT')
        console.log('APP DATA: ', data)
        // clear local storage
        localStorage.removeItem("checklist");
    }

    onMount(clearLocalStorage);
</script>

<header>
    <h1>Vancouver International Wine Festival tasting room checklist: Wines to try</h1>
    <!-- <p class="subhead">Everyone should have a plan of attack before arriving at the International Tasting Room, regardless of their level of knowledge or interest in wine.</p> -->
    <!-- <p class="subhead">With several hundred wines to taste, choosing themes can be a useful way of navigating the room. After reviewing the extensive list of tasting-room wines, we have some themes and recommendations.</p> -->
</header>

<main>
    <Checklist data={data.all} />
</main>
  
<style>
    @import '$css/normalize.css';
    @import '$css/fonts.css';
    @import '$css/colors.css';
    @import '$css/app.css';

    header {
		margin-bottom: 2rem;
	}
	header > h1 {
		text-align: center;
	}
	/* header .subhead {
		margin: 0 auto;
		max-width: 525px;
		text-align: center;
	} */

</style>
