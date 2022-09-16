<template>
    <button @click="play">Play</button>
</template>
<script setup lang="ts">
import * as Tone from 'tone'
const play = async () => {
    await Tone.start()
    const player = new Tone.Player({
        url: "rain-sounds.mp3",
        loop: true,
        autostart: false,
    }).toDestination()

    Tone.loaded().then(() => {
        player.start();
    });
}

</script>