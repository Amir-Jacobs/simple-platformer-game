# Simple Platformer Game

A small 2D platformer hobby project made in **Unity** (2019.3) back in 2020. The goal was to learn Unity basics by building a simple side-scrolling platformer from scratch.

## About

This was my first attempt at making a game. The project features a playable character that can run, jump, and interact with platforms using 2D physics. The player scripts are split into small, focused components following a modular design.

## Features

- **Horizontal movement** with configurable speed and physics-material switching (high friction when idle, no friction when moving) to prevent sliding
- **Jumping** with coyote time (~0.15s grace period after leaving a platform) and input buffering (~0.2s) for responsive controls
- **Variable gravity** — increased gravity on descent for snappier jump feel
- **Ground detection** via `Physics2D.OverlapBox`
- **Sprite flipping** based on movement direction
- **Animator-driven animations** — idle, running, jumping, and falling states
- **Dust particles** emitted while running
- **Smooth camera follow** using `Vector3.SmoothDamp`

## Project Structure

```
Assets/
├── Animations/              # Animation clips & controllers
├── PhysicsMaterials/        # 2D physics materials (high friction / no friction)
├── Scenes/
│   └── First Level.unity    # The single playable level
└── Scripts/
    ├── BackgroundFollow.cs  # (Stub) Background parallax — not yet implemented
    ├── CameraFollow.cs      # Smooth camera tracking of the player
    └── Player/
        ├── PlayerAnimation.cs    # Drives animator parameters based on state
        ├── PlayerDust.cs         # Plays dust particle effect while moving
        ├── PlayerFlip.cs         # Flips sprite to face movement direction
        ├── PlayerGrounded.cs     # Ground-check via overlap box cast
        ├── PlayerJump.cs         # Jump logic with coyote time & input buffering
        ├── PlayerJumpGravity.cs  # Adjusts gravity scale for better jump arc
        └── PlayerMovement.cs     # Horizontal movement & friction switching
```

## How to Open

1. Install **Unity 2019.3** (or a compatible later version).
2. Open the project folder in Unity Hub.
3. Open the **First Level** scene (`Assets/Scenes/First Level.unity`).
4. Press **Play** to run.

## Status

This was a learning project and is no longer actively developed.
