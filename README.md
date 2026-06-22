# Chess System Java

A complete implementation of the classic chess game in Java, featuring an interactive board representation and support for all standard chess rules including special moves.

## Overview

This project implements a fully functional chess game system with:
- **8x8 Chessboard** with graphical text-based UI
- **All Standard Chess Pieces**: Pawn, Rook, Knight, Bishop, Queen, and King
- **Complete Game Rules**: Check, checkmate, and stalemate detection
- **Special Moves**: Castling, En Passant, and Pawn Promotion
- **Turn-based Gameplay**: Alternating turns between White and Black players

## Game Rules

### Board Setup
- The chess game is played on an 8x8 board, totaling 64 squares
- Squares alternate between light and dark colors
- Players sit opposite each other, with the white pieces starting at ranks 1-2 and black pieces at ranks 7-8
- A white square is always positioned to the right of each player

### Piece Movement
Each piece has unique movement rules:

- **Pawn**: Moves forward one square (two on first move). Captures diagonally. Cannot move backwards.
- **Rook**: Moves any number of squares horizontally or vertically.
- **Knight**: Moves in an "L" shape (2 squares in one direction, 1 square perpendicular). Can jump over pieces.
- **Bishop**: Moves any number of squares diagonally.
- **Queen**: Combines rook and bishop movements (any squares horizontally, vertically, or diagonally).
- **King**: Moves one square in any direction.

### Game Objectives
- **Checkmate**: Put the opponent's king in check with no legal moves to escape → Win
- **Check**: Attack the opponent's king directly
- **Stalemate**: Opponent cannot move but is not in check → Draw
- **Threefold Repetition**: Same position repeats three times → Draw
- **Fifty-Move Rule**: 50 moves without capture or pawn movement → Draw

## Special Moves

### Castling
A special move involving the king and rook that allows the king to move two squares toward the rook.

**Requirements:**
- King has never moved
- Rook has never moved
- No pieces between king and rook
- King is not in check
- King does not pass through check
- King does not end in check

**Effect:** King moves 2 squares toward the rook, and the rook moves to the square the king crossed.

### En Passant
A special pawn capture that occurs when an opponent's pawn moves two squares forward from its starting position and lands beside your pawn.

**Requirements:**
- Opponent's pawn just moved two squares forward
- Your pawn is on its 5th rank (white) or 4th rank (black)
- The capture must occur immediately on the next move

**Effect:** Your pawn captures the opponent's pawn as if it had only moved one square.

### Promotion
When a pawn reaches the opposite end of the board (rank 8 for white, rank 1 for black), it is promoted to a more powerful piece.

**Promotion Options:**
- Queen (most common choice due to its power)
- Rook
- Bishop
- Knight

## Project Structure

```
src/
├── application/
│   ├── App.java          # Main entry point
│   └── UI.java           # User interface and board display
├── boardgame/
│   ├── Board.java        # 8x8 board management
│   ├── BoardException.java
│   ├── Piece.java        # Abstract piece class
│   └── Position.java     # Board position coordinates
└── chess/
    ├── ChessMatch.java   # Game logic and rule enforcement
    ├── ChessException.java
    ├── ChessPiece.java   # Chess-specific piece implementation
    ├── ChessPosition.java # Chess notation (e.g., e4, d8)
    ├── enums/
    │   └── Color.java    # Piece colors (WHITE, BLACK)
    └── pieces/
        ├── Bishop.java   # Bishop piece
        ├── King.java     # King piece
        ├── Knight.java   # Knight piece
        ├── Pawn.java     # Pawn piece (with promotion support)
        ├── Queen.java    # Queen piece
        └── Rook.java     # Rook piece
```

## Features

- ✅ All 6 piece types with authentic movement patterns
- ✅ Castling (kingside and queenside)
- ✅ En Passant pawn capture
- ✅ Pawn Promotion
- ✅ Check and Checkmate detection
- ✅ Turn-based gameplay
- ✅ Text-based UI with board visualization
- ✅ Move validation and error handling

## Running the Game

To compile and run the chess system:

```bash
javac -d bin src/**/*.java
java -cp bin application.App
```

Or use your IDE to run `App.java` directly.

## How to Play

1. The game displays the board with White pieces at the bottom and Black pieces at the top
2. Players enter moves using standard chess notation (e.g., `e2 e4`)
3. The system validates moves according to chess rules
4. Special moves (castling, en passant, promotion) are executed automatically when applicable
5. The game ends when checkmate, stalemate, or resignation occurs

## Technologies Used

- **Language**: Java
- **Architecture**: Object-Oriented Programming with inheritance and polymorphism
- **UI**: Console-based text interface

## Future Enhancements

- GUI implementation with Swing or JavaFX
- PGN (Portable Game Notation) support for saving/loading games
- AI opponent with difficulty levels
- Online multiplayer support
- Move history and game replay functionality


