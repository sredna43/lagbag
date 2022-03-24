<script>
import Content from "/src/shared/content.svelte";
import Header from "/src/shared/header.svelte";
</script>

<Header title="Minecraft Servers" pageTitle="Minecraft Servers" active = "/minecraft"/>
<Content class="page">
    <p><a href="/minecraft/enigmatica" class="enigmatica">Enigmatica 6 Expert</a></p>
    <p><a href="/minecraft/vanilla" class="vanilla">Vanilla 1.18.2</a></p>
</Content>

<style>
    a {
        text-decoration: none;
        font-size: 24px;
        padding: 12px;
        border-radius: 6px;
    }
    p {
        margin-top: 64px;
        text-align: center;
    }
    .enigmatica {
        color: black;
        background-color: rgb(48, 252, 242);
    }
    .vanilla {
        color: black;
        background-color: rgb(127, 165, 121);
    }
</style>