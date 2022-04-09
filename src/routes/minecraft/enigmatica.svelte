<script>
    import Pagenav from "/src/shared/pagenav.svelte";
    import Content from "/src/shared/content.svelte";
    import Header from "/src/shared/header.svelte";
    let view = "installation";
    let views = [
        {
            title: "Installation Guide",
            id: "installation"
        },
        {
            title: "Server Map",
            id: "map"
        }
    ]
</script>

<Header title="Minecraft Servers - Enigmatica 6 Expert" active="/minecraft" />
<Pagenav bind:active={view} options={views}/>
<Content>
    {#if view === "installation"}
    <div>
        <h1>Installation:</h1>
        <h2>Install Java:</h2>
        <p>The best java version I've found to work with this modpack is Java 8_312</p>
        <a class="javalink" href="https://github.com/adoptium/temurin8-binaries/releases/download/jdk8u312-b07/OpenJDK8U-jdk_x64_windows_hotspot_8u312b07.msi">Windows x64</a>
        <a class="javalink" href="https://github.com/adoptium/temurin8-binaries/releases/download/jdk8u312-b07/OpenJDK8U-jdk_x64_mac_hotspot_8u312b07.pkg">macOS x64</a>
        <h2>Install MultiMC:</h2>
        <ol>
            <li><p>We recommend using <a href="https://multimc.org/#Download">MultiMC</a> to handle all of your Minecraft instances. Follow the install steps on their website to get started.</p></li>
            <li>
                <p>You will most liekly want to set up MultiMC to track the development channel to get the newest features</p>
                <p>Click on settings -> Update Channel -> Development</p>
            </li>
            <li>
                <p>You'll probably want to make MultiMC look a little prettier as well...</p>
                <ol>
                    <li>
                        <p>Click on settings -> User Interface</p>
                    </li>
                    <li>
                        <p>Make any theme changes you want, I like Simple (Colored Icons) and Dark.</p>
                    </li>
                </ol>
            </li>
        </ol>
        <h2>Add Enigmatica 6 Expert Instance:</h2>
        <ol>
            <li><p>Open MultiMC</p></li>
            <li><p>Click on "Add Instance" in the top left corner</p></li>
            <li><p>Click on CurseForge</p></li>
            <li><p>Search for Enigmatica</p></li>
            <li><p>Select Enigmatica 6 Expert, version 1.1.2, and press "OK"</p></li>
        </ol>
        <h2>Set up JVM args and RAM</h2>
        <ol>
            <li><p>Click on your new Enigmatica 6 instance</p></li>
            <li><p>Click on "Edit Instance"</p></li>
            <li><p>Click on "Settings" then check the "Memory" and "Java arguments" box</p></li>
            <li><p>Set max ram to at least 5GB and at most 10GB</p></li>
            <li><p>(Optional) you may also want to set min ram to something like 2GB to smooth things out</p></li>
            <li>
                <p>Set "Java arguments" to the following:</p>
                <p>-XX:+UseG1GC -Dsun.rmi.dgc.server.gcInterval=2147483646 
                -XX:+UnlockExperimentalVMOptions -XX:G1NewSizePercent=20 
                -XX:G1ReservePercent=20 -XX:MaxGCPauseMillis=50 -XX:G1HeapRegionSize=32M</p>
            </li>
        </ol>
        <h2>Add the LAGbag server:</h2>
        <p>In the same "Edit Instance" window as the previous step, click on "Servers" -> "Add" and then add the details for the LAGbag Enigmatica 6 server</p>
        <p>Server IP: </p><p class="ip">enigmatica.lagbag.games</p>
        <h2>Launch!</h2>
        <p>You should be good to go, have fun!</p>
    </div>
    {:else if view === 'map'}
    <h1>Server Map</h1>
        <iframe src="https://map.lagbag.games" title="current player map"></iframe>
    {/if}
    
</Content>

<style>
    h1 {
        font-size: 56px;
        text-decoration: underline;
    }
    h2 {
        font-size: 48px;
    }
    li {
        font-size: 24px;
    }
    p {
        font-size: 24px;
    }
    .javalink {
        font-size: 24px;
        padding-right: 64px;
    }
    iframe {
        width: 100%;
        height: 700px;
    }
    .ip {
        text-decoration: underline;
        color: blue;
    }
</style>