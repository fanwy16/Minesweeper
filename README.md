# Minesweeper

A desktop Minesweeper game built with Java, Gradle, and the Processing graphics library. The game recreates the classic grid-based puzzle with randomized mine placement, flagging, recursive tile reveal, timer tracking, win/loss states, and animated mine explosions.

## Features

- Classic Minesweeper interaction: reveal tiles, flag suspected mines, and clear the board.
- Random mine placement on every new game.
- Configurable mine count from the command line.
- Recursive reveal for empty regions.
- Numbered tiles with color-coded adjacent mine counts.
- Right-click flag toggling.
- Game timer with win/loss stop states.
- Mine explosion animation when the player loses.
- Keyboard restart support.

## Tech Stack

- Java
- Gradle
- Processing Core
- JUnit 5 test setup

## Project Structure

| Path | Purpose |
| --- | --- |
| `src/main/java/minesweeper/App.java` | Main Processing application, game loop, input handling, timer, restart logic, and board setup. |
| `src/main/java/minesweeper/Tile.java` | Tile state and rendering logic, including reveal behavior, flags, mine counts, adjacency, and explosion frames. |
| `src/main/resources/minesweeper/` | Sprite assets for tiles, flags, and mine animation frames. |
| `build.gradle` | Gradle project configuration, dependencies, application entry point, test setup, and jar packaging. |

## Requirements

- Java 17 or later recommended
- Gradle wrapper included, so a local Gradle installation is not required

## Run

Clone the repository:

```bash
git clone https://github.com/fanwy16/Minesweeper.git
cd Minesweeper
```

Start the game with the default mine count:

```bash
./gradlew run
```

Start the game with a custom mine count:

```bash
./gradlew run --args="50"
```

On Windows:

```bash
gradlew.bat run --args="50"
```

## Controls

| Action | Control |
| --- | --- |
| Reveal tile | Left click |
| Place or remove flag | Right click |
| Restart game | `R` |

## Gameplay

The board is generated as a fixed-size grid. Mines are shuffled into random tile positions, and every non-mine tile stores the number of adjacent mines around it. Revealing a mine ends the game and triggers the mine animation. Revealing all non-mine tiles wins the game and stops the timer.

The command-line mine count lets you tune difficulty without changing the code:

```bash
./gradlew run --args="10"
./gradlew run --args="100"
```

## Build

Create a runnable jar:

```bash
./gradlew jar
```

Run tests:

```bash
./gradlew test
```

## License

This project is released under the MIT License. See `LICENSE` for details.
