# Asteroids

A 2D arcade-style **Asteroids** game built with **Python and Pygame**.

The project recreates the core gameplay of the classic Asteroids formula: control a spaceship, move around the play area, fire projectiles, and destroy incoming asteroids. The game uses object-oriented Python with separate classes for the player, asteroids, projectiles, and asteroid spawning.

## Technologies

* Python 3.13+
* Pygame 2.6.1
* Object-Oriented Programming
* Pygame Sprite Groups
* Vector-based movement and rotation
* Collision detection

## Features

* Player-controlled spaceship
* Keyboard movement and rotation
* Projectile firing with a shooting cooldown
* Random asteroid spawning from the edges of the screen
* Multiple asteroid sizes
* Asteroid splitting when hit
* Collision detection between the player, shots, and asteroids
* 60 FPS game loop
* Game-over state when the player collides with an asteroid
* Event/state logging for gameplay events

## Controls

| Action        | Key     |
| ------------- | ------- |
| Rotate Left   | `A`     |
| Rotate Right  | `D`     |
| Move Forward  | `W`     |
| Move Backward | `S`     |
| Shoot         | `SPACE` |

## How It Works

### Player

The player controls a triangular spaceship positioned in the center of the screen. Movement is calculated using Pygame vectors, allowing the ship to move in the direction it is facing. Rotation is controlled independently from movement.

### Asteroids

Asteroids spawn at random positions along the edges of the game window and travel toward the play area at randomized speeds and angles.

There are three asteroid sizes. When a larger asteroid is hit, it is destroyed and can split into two smaller asteroids traveling in different directions.

### Projectiles

The player can fire projectiles in the direction the ship is facing. A cooldown prevents the player from firing continuously without delay.

### Collision Detection

The game checks for collisions between:

* The player and asteroids
* Projectiles and asteroids

When a projectile hits an asteroid, the asteroid is split and the projectile is removed. When the player is hit, the game ends.

## Project Structure

```text
Asteroids/
├── asteroid.py          # Asteroid behavior and splitting
├── asteroidfield.py     # Asteroid spawning and movement setup
├── circleshape.py       # Base shape and collision functionality
├── constants.py         # Game configuration and constants
├── logger.py            # Gameplay/event logging
├── main.py              # Main game loop
├── player.py            # Player movement and shooting
├── shot.py              # Projectile behavior
├── pyproject.toml       # Project configuration and dependencies
└── uv.lock              # Locked Python dependencies
```

## Installation

Clone the repository:

```bash
git clone https://github.com/christopher-garcia1/Asteroids.git
cd Asteroids
```

Install the project dependencies:

```bash
uv sync
```

## Run the Game

```bash
uv run main.py
```

The game will open in a **1280 × 720** Pygame window and run at up to 60 frames per second.

## Configuration

Game settings such as screen size, player speed, asteroid spawning, projectile speed, and shooting cooldown are stored in `constants.py`.

```python
SCREEN_WIDTH = 1280
SCREEN_HEIGHT = 720
PLAYER_SPEED = 200
PLAYER_SHOOT_SPEED = 500
PLAYER_SHOOT_COOLDOWN_SECONDS = 0.3
ASTEROID_SPAWN_RATE_SECONDS = 0.8
```

## What I Learned

This project provided hands-on experience with:

* Python object-oriented programming
* Inheritance and reusable game objects
* Pygame's sprite system
* Game loops and frame timing
* Vector mathematics for movement
* Collision detection
* Managing multiple game objects with sprite groups
* Structuring a multi-file Python application


