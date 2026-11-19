# Space Invaders

A browser version of the 1978 arcade game, built as a single `index.html` file with vanilla JavaScript and an HTML5 canvas. It has no dependencies and no build step.

Defend the bottom of the screen against 55 marching invaders. Shoot them down, shelter behind the bunkers, and survive with three lives.

## Quick start

Open `index.html` in a desktop browser. There is nothing to install.

## Controls

| Key | Action |
| --- | --- |
| Left / Right arrow | Move the cannon |
| Space | Fire |
| P | Pause or resume |
| Enter | Start the game, or restart after game over |

On the game over screen you can also click the **Play Again** button.

## Gameplay

- Invaders move in discrete steps and drop one row each time the formation reaches a screen edge. A full formation steps every 500 ms, and the interval shrinks as invaders are destroyed.
- One hit destroys an invader. Squids score 30 points, crabs 20 and octopuses 10.
- You can have one bullet in flight at a time. Only the lowest invader in each column fires, with at most three invader bullets on screen.
- Four bunkers sit between you and the invaders. Bullets from either side erase a small area where they land.
- You start with three lives. A hit costs one life, and the cannon flashes briefly while it cannot be hit again.
- The game ends when you lose all lives or when an invader reaches your row. The game over screen shows your final score.
- Clearing every invader starts a faster, slightly lower wave with fresh bunkers. Your score carries over.

## Implementation notes

- **Sprites.** The three invader designs (squid, crab, octopus, two animation frames each) and the player cannon are decoded at load time from the original arcade ROM bytes, as documented in the [Computer Archeology Space Invaders disassembly](https://www.computerarcheology.com/Arcade/SpaceInvaders/Code.html). The canvas uses `image-rendering: pixelated`.
- **Collisions.** Hitboxes are 80% of sprite size, centred on the sprite.
- **Bunkers.** Each bunker is a grid of cells. An impact clears a ragged area around the first cell a bullet touches.
- **Audio.** Shooting, explosion and game over sounds are synthesised with the Web Audio API. No audio files are used. Browsers block audio until the page receives input, so sound starts on your first key press.
- **HUD.** The score uses a 5x7 bitmap font drawn on the canvas. Remaining lives appear as cannon icons below the ground line.
- **Loop.** Animation runs on `requestAnimationFrame` with a time-based update.

## Requirements

A desktop browser with canvas and Web Audio support, and a keyboard.
