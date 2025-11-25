# Number Guessing Game

## Overview
A Python-based number guessing game where players try to guess a randomly generated number within a limited number of tries. The game provides improtant feedback and analysis the player's guessing strategy.

## Features
- Random number generation between 1-100
- Input validation and error handling
- Limited attempts (7 trys)
- History tracking
- Probability analysis of winning chances
- Optimal strategy suggestions
- Userfriendly interface

## Technologies Used
- **Programming Language**: Python 3
- **Libraries**: random, sys, time, math,datetime
- **Tools**: Standard Python environment

## Installation & Setup

### Essential
- Python 3.6 or higher installed on your system

### Steps to Run
1. **Clone or Download the Script**
   ```bash
   # Save the code as number_guessing_game.py
   ```

2. **Run the Game**
   ```bash
   python number_guessing_game.py
   ```

3. **Follow On-screen Instructions**
   - Enter guesses when prompted
   - Receive feedback on each guess
   - View analysis at game end

## Testing Instructions

### Manual Testing
1. **Valid Input Testing**
   - Test with numbers within range (1-100)
   - Check for correct higher/lower feedback

2. **Invalid Input Testing**
   - Test with non-numeric inputs
   - Test with numbers outside range
   - Test duplicate guesses

3. **Game Flow Testing**
   - Test winning scenario
   - Test losing scenario
   - Verify number of attempt given

### Automated Testing
Create a test file `test_game.py`:
```python
import unittest
from unittest.mock import patch
import io
import sys

class TestNumberGuessingGame(unittest.TestCase):
    # Add test cases here
    pass

if __name__ == '__main__':
    unittest.main()
```

## Design Documentation

### Use Case Diagram
```
[Player] -> (Start Game)
[Player] -> (Enter Guess)
[Player] -> (View Feedback)
[Player] -> (See Analysis)
[System] -> (Generate Number)
[System] -> (Validate Input)
[System] -> (Calculate Probability)
```

### Workflow Diagram
```
Start → Generate Secret → Prompt Guess → Validate → Check Result
                                    ↓              ↓
                                Show Feedback  Win/Lose → Analysis
```

### Sequence Diagram
```
Player        System
  |             |
  |→ Start Game |
  |             |→ Generate Secret
  |← Prompt     |
  |→ Guess      |
  |             |→ Validate
  |             |→ Check
  |← Feedback   |
  |             |→ Repeat until win/lose
  |← Analysis   |
```

### Component Diagram
```
Main Game
├── Input Handler
├── Validator
├── Guess Analyzer
├── Probability Calculator
└── Strategy Advisor
```

## Design Decisions & Rationale

### 1. Input Validation
**Decision**: Implement complete input validation with user feedback
**Rationale**: Prevents crashes and provides clear guidance for wrong inputs

### 2. Limited Attempts
**Decision**: Set maximum attempts to 7
**Rationale**: Matches optimal binary search depth for range 1-100 (log₂(100) ≈ 7)

### 3. Probability Analysis
**Decision**: Includes winning probability calculation
**Rationale**: Provides educational feedback about search space reduction

### 4. Time Delays
**Decision**: Add 1-sec delays between interactions
**Rationale**: Improves readability and user experience

## Implementation Details

### Core Functions

#### `get_valid_guess(lower, upper, previous_guesses)`
- Handles user input with validation
- Prevents duplicate guesses
- Ensures range compliance

#### `analyze_guesses(guesses, secret, lower, upper)`
- Calculates remaining possible numbers
- Checks probability of winning
- Uses set operations for efficiency

#### `min_additional_tries(guesses, secret, lower, upper)`
- Implements binary search analysis
- Calculates optimal remaining tries
- Uses logarithmic complexity

## Screenshots
<img width="1398" height="930" alt="Screenshot 2025-11-23 180626" src="https://github.com/user-attachments/assets/3a2d8103-d27e-4699-85d6-82e6f7fd5e42" />
<img width="1405" height="922" alt="Screenshot 2025-11-23 180744" src="https://github.com/user-attachments/assets/b25df5c0-5d67-4b76-84c5-49e443298f31" />

### Gameplay Example
```
Welcome to the Number Guessing Game!
Guess the number between 1 and 100. You have 7 tries.
Enter your guess (1-100): 50
Try a higher number.
Enter your guess (1-100): 75
Try a lower number.
Enter your guess (1-100): 63
Congratulations! You guessed the number 63 in 3 tries.
```

### Analysis Example
```
Based on your answers, your probability of winning was approximately 45.00%.
Based on your guesses so far, you could have found the secret number in about 2 more optimally chosen guesses.
```

## Testing Approach

### Unit Tests
- Input valedation testing
- Probability calculation varification
- Game logic valedation

### Integration Tests
- Full game flow tests
- Error handling scenarios
- Boundary condition testing

## Challenges Faced

1. **Probability Calcules**
   - Challenge: Correct modeling search space reduction
   - Solution: Used set operations to track remaining possibilities

2. **User Experience**
   - Challenge: Balancing feedback with game flow
   - Solution: Implemented timed delays and clear messages

3. **Optimal Strategy Analysis**
   - Challenge: Calculating minimum additional tries
   - Solution: Useing binary search principle to reduced range

## Learnings & Key Takeaways

1. **Algorithm Design**: Real world uses of binary search and probability theory
2. **User Input Handling**: Strong checking makes an application more reliable
3. **Educational Value**: Game mechanics can teach fundamental ComputerSience concepts
4. **Code Organization**: Dividing code into parts makes it easier to maintain

## Future Enhancements

1. **Difficulty Levels**
   - Easy: 1-50, 10 attempts
   - Medium: 1-100, 7 attempts (current)
   - Hard: 1-200, 8 attempts

2. **Additional Features**
   - Score tracking system
   - Graphical user interface
   - Multiplayer mode
   - Hint system

3. **Technical Improvements**
   - Database integration for high scores
   - Web-based interface
   - Mobile app version

## References

- Python Official Documentation: https://docs.python.org/3/
- Binary Search Algorithm: Classical computer science algorithm
- Probability Theory: Basic principles of search space reduction


