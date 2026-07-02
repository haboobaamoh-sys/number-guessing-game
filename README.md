# My Number Guessing Game

This is a console game built using Java. I designed it using OOP principles by separating the game into 3 main classes to keep everything neat and organized.

## What it can do:
- It picks a random number between 1 and 100.
- Gives the player 10 turns to guess the right number.
- Shows hints after every guess: "Too High" or "Too Low".
- Input Validation: If you enter letters or numbers out of range, it warns you and doesn't crash.
- It asks if you want to play another match when you finish.

## Project Structure (UML Diagram)
This diagram shows how my classes communicate:

```mermaid
classDiagram
    class Main {
        +main(args: String[]) void
    }
    class GameEngine {
        -secretNumber: int
        -maxAttempts: int
        -attemptsUsed: int
        +checkGuess(guess: int) String
        +getRemainingAttempts() int
        +isGameOver() boolean
    }
    class InputValidator {
        +getValidGuess(min: int, max: int, current: int, total: int) int
        +askToPlayAgain() boolean
    }

    Main --> GameEngine : Uses
    Main --> InputValidator : Uses
