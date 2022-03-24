<script lang="ts">
    import { page } from "$app/stores";
    export let active = '/';
    let links = [
        {
            title: 'Home',
            to: '/'
        },
        {
            title: 'Minecraft Servers',
            to: '/minecraft'
        },
        {
            title: 'Projects',
            to: '/projects'
        }
    ]    
</script>

<ul>
    {#each links as link}
        <li class={link.to === active ? 'active' : ''}>
            <a href={link.to} class={link.to === active ? 'active' : ''}>{link.title}</a>
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

	li a {
		display: block;
		color: black;
		text-align: center;
		padding: 28px 32px;
		text-decoration: none;
        font-size: 20px;
	}

	/* Change the link color to #111 (black) on hover */
	li a:hover {
		background-color: rgb(72, 102, 47);
        color: white;
	}

    .active {
        background-color: rgb(72, 102, 47);
        color: white;
    }
</style>