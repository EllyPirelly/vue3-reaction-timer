# Vue 3 CLI - Reaction Timer

## What is this about?
- a simple Vue 3 CLI set-up with a reaction timer
- click the play button
- after a delay (a time between 2 and 7 seconds, calculated with Math.random) a buzzer appears you should click immediately
- the time it took you to click that buzzer is measured and displayed as a result
- this project only has the bare minimum regarding styling, focus is on understanding Vue

## How does it work
- when the component mounts, it takes a specified delayed time before a green buzzer appears
- when the green buzzer first shows up, a timer is started, it goes up in incremented 10 milliseconds
- the time is stored in `reactionTime`
- click on green buzzer
- interval is cleared so `reactionTime` will no longer keep going up but will store the time at the point of clicking
- the result is shown to the user via `results` component
- we get the data from the `block` component back up to the `app` component via emitting a custom event from the `block` component
- we listen to that custom event in the `app` component, on the `block` component
- we call the function attached to it
- inside that function we are updating the score
- we stop olaying
- we output the score
- so we added a custom event and a callback function to call an emitted event inside of the `app` component

## Tech Stack
- Vue 3
- HTML, SCSS, JavaScript

## Source
- [The Net Ninja - Vue JS 3 Tutorial for Beginners #6 - Reaction Timer](https://www.youtube.com/watch?v=bc6czIBLKTg&list=PL4cUxeGkcC9hYYGbV60Vq3IXYNfDk8At1&index=7)
- [GitHub - result Branch](https://github.com/iamshaunjp/Vue-3-Firebase/tree/lesson-37)

## How to run this?
- clone the repo
- cd into project
- `npm install` to prepare the project setup
- `npm run serve` to compile and hot-reaload for development, this will generally fire up the server at http://localhost:8080/ (or the next availble number)
- `npm run build` to compile and minify for production
- `npm run lint` to lint and fix files
- `control c` to properly stop the server

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
