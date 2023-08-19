<script>
	import { Canvas } from '@threlte/core';
	import Pong from './Pong.svelte';
</script>

<div class="w-screen h-screen">
	<Canvas frameloop="demand" debugFrameloop={false}>
		<Pong />
	</Canvas>
	<p>Supposedly takes the width of parent element</p>
</div>
