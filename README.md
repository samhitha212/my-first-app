# AI Coding Journey — Quote Generator

A single-page quote generator built with vanilla HTML, CSS, and JavaScript. Clicking a button selects a random quote from a JavaScript array and swaps it into the page with a fade transition. Built with no frameworks, no build step, and no dependencies.

## Project Description

The entire application lives in one self-contained `index.html` file — markup, styles, and logic. A hardcoded array holds the quote collection, and a `generateNewQuote()` function picks an index at random, updates the DOM, and drives a CSS fade-out/fade-in animation via class toggling and a short `setTimeout` to sequence the two halves of the transition.

The goal of the project was to practice core browser fundamentals directly, without a library abstracting them away.

## Features

- **Dark Mode UI** — Deep navy gradient background (`#1a1a2e` → `#16213e`) with light text for comfortable reading
- **Neon Glow Accents** — Cyan text-shadow on the heading and a glowing box-shadow on the button that intensifies and lifts on hover
- **Dynamic Quote Selection** — Random quote chosen at runtime from a JavaScript array on every click
- **Frosted Glass Card** — Translucent container using `backdrop-filter: blur()` over the gradient background
- **Fade Transitions** — Quotes cross-fade using CSS keyframe animations and transition classes toggled from JavaScript
- **Fluid Layout** — Flexbox centering with a `max-width` card that adapts down to smaller viewports
- **Zero Dependencies** — No frameworks, no build tooling, no install step

## Engineering Concepts Learned

- **Arrays** — Storing the quote collection in a `const` array and accessing elements by index (`quotes[currentIndex]`), using `.length` to keep selection in bounds as the array grows
- **`Math.random()` and `Math.floor()`** — Combining the two into the standard random-index formula, `Math.floor(Math.random() * quotes.length)`. `Math.random()` returns a float in `[0, 1)`, multiplying by the array length scales it to `[0, length)`, and `Math.floor()` truncates to a valid integer index
- **Event-Driven Functions** — Wiring a named function to a user action through an `onclick` handler, so UI updates are triggered by events rather than running top to bottom
- **DOM Manipulation** — Selecting an element with `getElementById`, rewriting its `textContent`, and toggling CSS classes with `classList.add()` / `.remove()` to change appearance from JavaScript
- **Async Timing with `setTimeout`** — Delaying the text swap by 300ms so the fade-out finishes before the new quote appears, coordinating JavaScript with CSS animation duration
- **CSS Animation** — Writing `@keyframes`, transitions, and transforms to create motion without JavaScript animation loops

## Getting Started

No installation or build required.

1. Clone or download the repository
2. Open `index.html` directly in any modern browser
3. Click **Generate New Quote**
## Project Structure

```
my-first-app/
└── index.html    # Markup, styles, and script in one file
```

## Technologies Used

- **HTML5** — Semantic document structure
- **CSS3** — Gradients, `backdrop-filter`, keyframe animations, transitions, flexbox
- **JavaScript (ES6)** — `const`/`let`, arrow functions, DOM APIs

## Possible Next Steps

- Move to `addEventListener` and separate `.css` / `.js` files as the project grows
- Prevent the same quote from being selected twice in a row
- Add quote attribution and a copy-to-clipboard action
- Add `@media` queries for finer control over small-screen typography
