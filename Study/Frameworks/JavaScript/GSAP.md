---
sticker: lucide//chevron-up
---
# Packages to install

1. TimelineLite
2. CSSPlugin
3. TweenLite

Order matters, and link your js file after this.
### Basic syntax
```javascript
const tween = TweenLite.to(object, time, {animate})
```

### Example
```javascript
const navButton = document.queryselector('.nav-button')
const navOpen = document.querySelector('.nav-open')

const tween = TweenLite.to('.cover' 1, {
	width: "40%"
	ease: Power2.easout
}).to('nav', 1, {
	height: '100%'
	ease: Power2.easeout
})

navButton.addEventListener('click', ( => {
	tl.play();
}))
```

- `tl` stands for timeline which is built in function in gsap.
- `play()` is built in function for playing transition in `tl.play()`.
- Programmer can also create a timeline of transition with `to` and `fromTo` functions.

### `to` function
It uses for animating current phase of element to another phase.

### `from` function
It uses for animating new phase of element to current of element.

### `fromTo` function
It uses for animating new phase of element to another of element.
```javascript
const example = TweenLite.to('.cover' 1, {
	width: "40%"
	ease: Power2.easout
}).to('nav', 1,
	  {
		height: '100%'
		ease: Power2.easeout
	},
	{
		height: '50%'
		ease: Power2.easeout
	}
) 
```

### Delay in animation
before parentheses and after curly brackets defined integer indicates function delay.
```javascript
const example = TweenLite.to('.cover' 1, {
	width: "40%"
	ease: Power2.easout
}, 0.5).to('nav', 1, {
	height: '100%'
	ease: Power2.easeout
}, =-0.5) // It will execute 0.5 minute ago
```

### Different states in a single animation
use multiple curly bracket blocks for multiple states within parentheses.