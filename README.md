# Monad Test

This Jupyter notebook demonstrates **Writer Monads** in Python, applying them to game logic for tracking state changes.

## Key Contents

**WriterMonad Implementation**

- A simple monad class that pairs a value with a log (list)
- `bind()` method chains operations while accumulating logs
- Includes `__eq__` for unit testing

**Basic Example**

- Chains string operations with the monad, accumulating log entries
- Demonstrates how logs from each step are collected into a list

**Game Logic Application**

- Defines a `gameData` dataclass with player IDs, health, and debuffs
- `applyDamage()` function modifies game state imperatively
- `writerApplyDamage()` wraps this in a monad, using `deepcopy` to log state snapshots

**Monadic Chain Demo**

- Shows damage being applied to player 3 twice using monad binding
- The log captures the full game state after each damage application
- Result: `player_id=3, health=[100, 85, 60, 90, 75]` (after two 20-damage hits)

**Unit Tests**

- Two test classes verify basic monad behavior and the game logic example
- Both pass successfully

The notebook illustrates how monads can abstract state mutations while maintaining a clear audit trail—useful for game replay, debugging, or undo functionality.

##### Sources
https://www.youtube.com/watch?v=roP_HC7tiXw

https://www.youtube.com/watch?v=VgA4wCaxp-Q
