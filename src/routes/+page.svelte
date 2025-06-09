<script lang="ts">
	let rightSound: HTMLAudioElement | null = null;
	let wrongSound: HTMLAudioElement | null = null;

	const playRightSound = () => {
		if (rightSound) return rightSound.play();
	};
	const playWrongSound = () => {
		if (wrongSound) return wrongSound.play();
	};
</script>

<!-- Audio element with a reference bound -->
<audio bind:this={rightSound} src="right.mp3" preload="auto"></audio>
<audio bind:this={wrongSound} src="wrong.mp3" preload="auto"></audio>

<div class="flex h-svh flex-col items-center justify-center gap-10 bg-slate-800">
	<!-- Button to trigger the sound effect -->

	<button
		class="size-30 rounded-full bg-emerald-400 hover:cursor-pointer active:scale-95 active:bg-emerald-700 active:opacity-95"
		on:click={playRightSound}
	>
		<img src="thumbs-up.png" alt="A thumbs-up button" />
	</button>
	<button
		class="size-30 rounded-full bg-red-300 hover:cursor-pointer active:scale-95 active:bg-red-600 active:opacity-95"
		on:click={playWrongSound}
	>
		<img src="thumbs-down.png" alt="A thumbs-down button" />
	</button>
</div>
