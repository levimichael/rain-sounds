<template>
    <button @click="play">Play</button>
</template>
<script setup lang="ts">
import * as Tone from 'tone'
const play = async () => {
    const player = new Tone.Player({
        url: "https://cdabf9b7b8ceefdf343dfe261084d747.r2.cloudflarestorage.com/leviwhalen/rain-sounds.mp3",
        loop: true,
        autostart: false,
    }).toDestination()

    Tone.loaded().then(() => {
        player.start();
    });
}

</script>