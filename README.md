# monad-test1

This Jupyter notebook demonstrates Writer Monad implementation in Python with practical game logic applications.
Key Sections:

1. WriterMonad Class A basic monad implementation with:

    value: holds the wrapped value
    log: accumulates a list of logs from each bind operation
    bind(): chains operations and combines logs
    __eq__(): enables unit testing

2. Initial Playground Tests the monad with simple string operations, demonstrating how logs accumulate through chained bind calls.

3. Game Logic Defines a gameData dataclass to represent game state (player IDs, health, debuffs) and an applyDamage() function that modifies game state imperatively.

4. Monad + Game Logic Combines the WriterMonad with game operations using writerApplyDamage(), which:

    Applies damage to a player
    Logs a deep copy of the entire game state after each operation
    Returns a WriterMonad for chaining

5. Unit Tests Two test suites verify:

    Basic monad behavior with string/dict operations
    Game monad behavior, confirming damage is applied correctly and state history is logged

Result: The notebook successfully demonstrates how monads can track side effects (game state changes) in a functional programming style, creating an immutable log of all intermediate game states through chained operations.
