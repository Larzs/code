## CSS

### @media prefers-color-scheme

```
@media (prefers-color-scheme: dark) {
    :root {
        color-scheme: dark;
        
        --brand: var(--brand-dark);
        --text: var(--text-dark);
        --bg1: var(--bg1-dark);
        --surface1: var(--surface1-dark);
    }
}
```

### Loader

<style>
.spinner, .spinner * {
    box-sizing: border-box;
}
  
.spinner {
    height: 35px;
    width: 35px;
    border-radius: 50%;
    perspective: 800px;
}
    
.spinner__slice {
    position: absolute;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    border-radius: 50%;
}

.spinner .spinner__slice:nth-child(1) {
    left: 0%;
    top: 0%;
    animation: orbit-spinner-orbit-one-animation 1200ms linear infinite;
    border-bottom: 3px solid #ff1d5e;
}

.spinner .spinner__slice:nth-child(2) {
    right: 0%;
    top: 0%;
    animation: orbit-spinner-orbit-two-animation 1200ms linear infinite;
    border-right: 3px solid #ff1d5e;
}

.spinner .spinner__slice:nth-child(3) {
    right: 0%;
    bottom: 0%;
    animation: orbit-spinner-orbit-three-animation 1200ms linear infinite;
    border-top: 3px solid #ff1d5e;
}

@keyframes orbit-spinner-orbit-one-animation {
    0% {
        transform: rotateX(35deg) rotateY(-45deg) rotateZ(0deg);
    }
    100% {
        transform: rotateX(35deg) rotateY(-45deg) rotateZ(360deg);
    }
}

@keyframes orbit-spinner-orbit-two-animation {
    0% {
        transform: rotateX(50deg) rotateY(10deg) rotateZ(0deg);
    }
    100% {
        transform: rotateX(50deg) rotateY(10deg) rotateZ(360deg);
    }
}

@keyframes orbit-spinner-orbit-three-animation {
    0% {
        transform: rotateX(35deg) rotateY(55deg) rotateZ(0deg);
    }
    100% {
        transform: rotateX(35deg) rotateY(55deg) rotateZ(360deg);
    }
}
</style>

<div class="spinner">
    <div class="spinner__slice"></div>
    <div class="spinner__slice"></div>
    <div class="spinner__slice"></div>
</div>

### Box Shadow

<style>
	.gradient-shadow:before {
		content:  '';
		position:  absolute;
		inset: 0;
		background: red;
		z-index: -1;
		border-radius: inherit;
		transform: translateY(15%) scale(0.85);
		filter:  blur(30px) brightness(1.5);
		background: var(--gradient);
	}

	.gradient-shadow {
	    --gradient: linear-gradient(to bottom right, lime, cyan);

	    background:  var(--gradient);
	    inline-size: 75vmin;
	    aspect-ratio: 4/3;
	    border-radius: 1rem;
	    position: relative;
    }
	</style>

<div class="gradient-shadow"></div>
