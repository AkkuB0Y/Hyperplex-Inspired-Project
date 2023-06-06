<div id="wrapper" data-configuration="1" data-roundness="1">
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
</div>

<h style="font-size: 2rem; color: #fafafa"> 
    Project by <span style="color: #9b70ff">Akshay Satish. </span></h>

<h style="font-size: 2rem; color: #fafafa"> Inspired by <span style="color: #baf3df">Hyperplexed.</span> Assisted by <span style="color: #16cbd5">Omar Usman.</span></h>

<a target="_blank" class="link-btn" href="https://www.youtube.com/@Hyperplexed">Hyperplexed's YT Channel</a>
<a target="_blank" class="link-btn" href="https://www.github.com/OmarUsman">Omar Usman's GitHub</a> 


<script>
    import { onMount } from 'svelte';
    onMount(async () => {
        const wrapper = document.getElementById("wrapper");

        const rand = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);

        const uniqueRand = (min, max, prev) => {
        let next = prev;
        
        while(prev === next) next = rand(min, max);
        
        return next;
        }

        const combinations = [
        { configuration: 1, roundness: 1 },
        { configuration: 1, roundness: 2 },
        { configuration: 1, roundness: 4 },
        { configuration: 2, roundness: 2 },
        { configuration: 2, roundness: 3 },
        { configuration: 3, roundness: 3 }
        ];

        let prev = 0;

        setInterval(() => {
        const index = uniqueRand(0, combinations.length - 1, prev),
                combination = combinations[index];
        
        wrapper.dataset.configuration = combination.configuration;
        wrapper.dataset.roundness = combination.roundness;
        
        prev = index;
        }, 2000);
    });
</script> 
