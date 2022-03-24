<script lang="ts">
    export let active = '';
    export let options = [
        {
            title: 'Home',
            id: 'home'
        },
        {
            title: 'Minecraft Servers',
            id: 'mc'
        },
        {
            title: 'Projects',
            id: 'projects'
        }
    ]
    
</script>

<ul>
    {#each options as option}
        <li class={option.id === active ? 'active' : ''}>
            <button class={option.id === active ? 'active' : ''} on:click={() => active = option.id}>{option.title}</button>
        </li>
    {/each}
</ul>

<style>
    ul {
		list-style-type: none;
		margin: 0;
		overflow: hidden;
		background-color: rgb(230, 217, 207);
	}

	li {
        float: left;
	}

	li button {
		display: block;
		color: black;
		text-align: center;
		padding: 28px 32px;
		text-decoration: none;
        font-size: 20px;
	}

	/* Change the option color to #111 (black) on hover */
	li button:hover {
		background-color: rgb(72, 102, 47);
        color: white;
	}

    .active {
        background-color: rgb(72, 102, 47);
        color: white;
    }
</style>