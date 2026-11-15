# PongProject
# Pong Game – Lab 2 Report

## 1. Team and Contribution

**Team members:** Daniel Drozdziel U281595 and Izan Fouquet U282272
We were together working on the whole project.

## 2. Overview of Our Design

We implemented a Pong game using Python and Pygame. The program is divided into functions, with each function responsible for a specific task. This makes the code easier to understand, test and maintain.

The program starts by asking the user to choose the game configuration. The configuration functions read values such as screen dimensions, paddle settings and ball settings. They also check that the entered values are valid.

After configuration, the main function starts the game. The main loop handles keyboard input, updates the positions of the ball and paddles, checks collisions, updates the score and draws the game on the screen.

The functions pass information through parameters and return values instead of relying on global variables for changing game data. For example, the ball's position and speed are passed to the movement and collision functions. The configuration values are also passed to the functions that need them.

This structure separates the different parts of the game and makes it easier to find and fix problems.

## 3. Key Implementation Decisions

### Ball-paddle collision

One important part of the game is detecting when the ball hits a paddle.

We use rectangle collision detection. The ball and paddle have positions and dimensions, and the program checks whether their rectangles overlap.

When a collision happens, the horizontal speed of the ball is reversed. This makes the ball move in the opposite direction.

We also reposition the ball just outside the paddle after the collision. This is important because otherwise the ball could remain inside the paddle and trigger the collision repeatedly. Repositioning it helps prevent the ball from getting stuck.

### Input validation in the configuration menu

We added input validation so that the program does not crash when the user enters an invalid value.

The program uses `int()` to convert the input into an integer. This conversion is inside a small `try` block.

If the input cannot be converted, Python raises `ValueError`. The program catches this exception and asks the user to try again.

After conversion, the program checks whether the number is inside the allowed range. If it is too small or too large, an error message is displayed and the user is asked again.

Examples of invalid input include:
- Letters instead of numbers.
- Empty input when a number is required.
- Decimal numbers.
- Negative values when they are not allowed.
- Values outside the permitted range.

We also implemented a default-value option. The user can press ENTER to accept the suggested value instead of typing a number.

### Other implementation decisions

We kept the program simple and used separate functions for tasks such as moving the ball, checking collisions and displaying messages. This makes each part easier to understand.

We also changed the left paddle's downward control to the D key, so the left paddle uses A and D. The right paddle uses the arrow keys.

Any differences from the original docstrings should be explained here with the actual function name and reason.

## 4. Problems and Solutions

During development, we encountered some problems and made changes to solve them.

- **Invalid configuration input:** Invalid values could cause problems when converting input to integers. We used `try` and `except ValueError` and added range checks.
- **Ball collision:** The ball could remain in contact with a paddle after a collision. We repositioned the ball outside the paddle after reversing its horizontal speed.
- **GitHub commit:** At first, the commit did not appear on GitHub because it had not been pushed. We used Git push to upload the commit.

These problems were found while reviewing the code and testing the different parts of the program.

## 5. Testing

We checked the game using different inputs and situations.

- Tested valid configuration values.
- Tested letters, empty input and decimal numbers.
- Tested negative and out-of-range values.
- Tested the minimum and maximum allowed values.
- Checked the paddle controls.
- Checked ball movement and paddle collisions.
- Checked scoring and the game-over message.
- Tested the computer opponent.


## 6. Optional Features

We implemented the following optional features:

- **Default configuration values:** The user can press ENTER to accept the suggested default value.
- **Computer opponent:** The computer paddle follows the ball's position and tries to hit it.
- **Display messages:** The game displays messages, including the game-over message.

We also changed the main function so that the user is asked whether they want to play against the computer. The answer is stored in a variable and used by the main game loop to decide whether the computer paddle should move automatically.

## 7. Use of AI Tools

We used ChatGPT to help us only to understand difficult parts of the program.
