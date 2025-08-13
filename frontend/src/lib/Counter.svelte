<script lang="ts">
    import { Greet } from "../../wailsjs/go/main/App";

    let greeting: string = $state("This is Wails!");
    let name: string = $state("");
    const greet = () => {
        Greet(name).then((result) => (greeting = result));
    };
</script>

<div class="hero">
    <div class="hero-content flex-col">
        <p class="self-center mt-5 text-2xl">{greeting}</p>
        <div>
            <input
                class="input w-full m-10"
                placeholder="Enter name here..."
                bind:value={name}
            />

            <button class="btn btn-primary mx-10 w-full" onclick={greet}>
                Greet
            </button>
        </div>
    </div>
</div>
