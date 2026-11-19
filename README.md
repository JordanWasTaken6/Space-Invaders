# Space Invaders

A browser clone of Space Invaders in a single `index.html` file. It uses vanilla JavaScript and an HTML5 canvas. No frameworks, no libraries, no build step.

## Play

Open `index.html` in any modern browser.

## Controls

| Key | Action |
| --- | --- |
| Left / Right arrow | Move your ship |
| Space | Fire |
| P | Pause or resume |
| Enter | Start the game, or restart after game over |

## Features

- Coloured invaders drawn from the classic pixel sprites, with two animation frames.
- Invaders march side to side and drop one row at each edge. They speed up as you destroy them.
- Both you and the invaders fire. One hit destroys an invader.
- Three lives. You blink for two seconds after a hit.
- Scoring: top row 30 points, middle rows 20, bottom rows 10.
- Clearing a wave starts a faster, slightly lower wave. Your score carries over.
- Start screen, pause screen and game over screen.
- Sound effects for shooting, explosions and game over, generated with the Web Audio API. There are no audio files.

## Game rules

- You lose a life when an invader bullet hits your ship.
- The game ends when you lose all three lives or when invaders reach your row.
- Only one of your bullets can be on screen at a time.
- Only the lowest invader in each column can fire, and no more than three invader bullets can be on screen at once.

## Notes

- Browsers block audio until you interact with the page. Sound starts on your first key press.
- The game is written for desktop browsers with a keyboard.
