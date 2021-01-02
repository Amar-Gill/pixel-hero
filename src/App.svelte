<script>
	export let spriteStatus = "idle";
</script>

<style>
	div {
		width: calc(64px * var(--pixel-size));
		height: calc(64px * var(--pixel-size));
		position: relative;
		overflow: hidden;
	}

	img {
		width: calc(1024px * var(--pixel-size));
		position: absolute;
		image-rendering: crisp-edges;
		animation: moveSpriteSheet 1s steps(var(--num-frames)) infinite;
	}

	.idle {
		--num-frames: 4;
	}

	.walk {
		--num-frames: 8;
		top: calc(-64px * 1 * var(--pixel-size));
	}

	.jump {
		--num-frames: 8;
		top: calc(-64px * 2 * var(--pixel-size));
	}

	.spin {
		--num-frames: 10;
		top: calc(-64px * 3 * var(--pixel-size));
	}

	.down {
		--num-frames: 9;
		top: calc(-64px * 4 * var(--pixel-size));
	}

	.power-shot {
		--num-frames: 7;
		top: calc(-64px * 5 * var(--pixel-size));
	}

	.fast-shot {
		--num-frames: 6;
		top: calc(-64px * 6 * var(--pixel-size));
	}

	.flying-kick {
		--num-frames: 8;
		top: calc(-64px * 7 * var(--pixel-size));
	}

	.super-uppercut {
		--num-frames: 13;
		top: calc(-64px * 8 * var(--pixel-size));
	}

	.one-two-combo {
		--num-frames: 10;
		top: calc(-64px * 9 * var(--pixel-size));
	}

	.low-kick {
		--num-frames: 6;
		top: calc(-64px * 10 * var(--pixel-size));
	}

	.mid-kick {
		--num-frames: 6;
		top: calc(-64px * 10 * var(--pixel-size));
		left: calc(-64px * 6 * var(--pixel-size));
	}

	.high-kick {
		--num-frames: 6;
		top: calc(-64px * 11 * var(--pixel-size));
	}

	.down-kick {
		--num-frames: 8;
		top: calc(-64px * 12 * var(--pixel-size));
	}

	.two-side-attack {
		--num-frames: 8;
		top: calc(-64px * 13 * var(--pixel-size));
	}

	.round-kick {
		--num-frames: 8;
		top: calc(-64px * 14 * var(--pixel-size));
	}

	.uppercut {
		--num-frames: 6;
		top: calc(-64px * 15 * var(--pixel-size));
	}
	
	@keyframes moveSpriteSheet {
		from {
			transform: translate3d(0px, 0, 0);
		}
		to {
			transform: translate3d(
				calc(-64px * var(--pixel-size) * var(--num-frames)),
				0,
				0
			);
		}
	}
</style>

<div>
	<img
		class:idle={spriteStatus == 'idle'}
		class:walk={spriteStatus == 'walk'}
		class:jump={spriteStatus == 'jump'}
		class:spin={spriteStatus == 'spin'}
		class:down={spriteStatus == 'down'}
		class:power-shot={spriteStatus == 'power-shot'}
		class:fast-shot={spriteStatus == 'fast-shot'}
		class:flying-kick={spriteStatus == 'flying-kick'}
		class:super-uppercut={spriteStatus == 'super-uppercut'}
		class:one-two-combo={spriteStatus == 'one-two-combo'}
		class:low-kick={spriteStatus == 'low-kick'}
		class:mid-kick={spriteStatus == 'mid-kick'}
		class:high-kick={spriteStatus == 'high-kick'}
		class:down-kick={spriteStatus == 'down-kick'}
		class:two-side-attack={spriteStatus == 'two-side-attack'}
		class:round-kick={spriteStatus == 'round-kick'}
		class:uppercut={spriteStatus == 'uppercut'}
		src="/spritesheet.png"
		alt="sprite" />
</div>
<footer>
	<button on:click={() => (spriteStatus = 'idle')}>Idle</button>
	<button on:click={() => (spriteStatus = 'walk')}>Walk</button>
	<button on:click={() => (spriteStatus = 'jump')}>Jump</button>
	<button on:click={() => (spriteStatus = 'spin')}>Spin</button>
	<button on:click={() => (spriteStatus = 'down')}>Down</button>
	<button on:click={() => (spriteStatus = 'power-shot')}>Power Shot</button>
	<button on:click={() => (spriteStatus = 'fast-shot')}>Fast Shot</button>
	<button on:click={() => (spriteStatus = 'flying-kick')}>Flying Kick</button>
	<button on:click={() => (spriteStatus = 'super-uppercut')}>Super Uppercut</button>
	<button on:click={() => (spriteStatus = 'one-two-combo')}>One Two Combo</button>
	<button on:click={() => (spriteStatus = 'low-kick')}>Low Kick</button>
	<button on:click={() => (spriteStatus = 'mid-kick')}>Mid Kick</button>
	<button on:click={() => (spriteStatus = 'high-kick')}>High Kick</button>
	<button on:click={() => (spriteStatus = 'down-kick')}>Down Kick</button>
	<button on:click={() => (spriteStatus = 'two-side-attack')}>Two Side Attack</button>
	<button on:click={() => (spriteStatus = 'round-kick')}>Round Kick</button>
	<button on:click={() => (spriteStatus = 'uppercut')}>Uppercut</button>
</footer>
