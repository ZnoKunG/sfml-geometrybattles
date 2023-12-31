# SFML Geometry Battles
This is a 2D shooting game created using C++ and SFML. This is based on a simple 2D game engine using ECS architecture where it can create entity and attach components to it.

This project architecture composes of following:


    GameEngine               	  # Read config file and run all system functions
    ├── Systems             	  # Access entity manager to get certain type of entity and implement logics on the component
        ├── EntityManager          # Manage entities including create new entity, remove entity, and provide entity for system to use
            ├── Entity          	  # Contain all components which can be modified from system
                ├── Component 	  # composes of many components which can be attached to any entity. Ex.player has CTransform, CShape, CCollision, CInput

There are several aspects which can be improved and optimized for example, in the entity class it just stores all components. We can use std::vector or std::tuple to store all components and provide functions to add and get components.

All codes are built from the ground up and it is quite challenging in both my C++ unfamiliarity and complicated project architectural design. This game engine has no UI to adjust value but it is configured by config.txt to change and play around with the value in the game.

# Configuration File
- Window (width) (height) (frame limit) (is full screen mode)
- Font (font file) (font size) (r) (g) (b)
- Player (shape radius) (collision radius) (fill color) (outline color) (outline thickness) (shape vertices) (speed)
- Enemy (shape radius) (collision radius) (outline color) (outline thickness) (min vertices) (max vertices) (small lifespan) (spawn interval(in frames)) (min speed) (max speed)
- Bullet (shape radius) (collsiion radius) (fill color) (outline color) (outline thickness) (shape vertices) (lifespan (in frames)) (speed)
- Special (shape radius) (collsiion radius) (speed) (fill color) (outline color) (outline thickness) (shape vertices) (trigger duration) (trigger radius) (cooldown) (speed) (vec2 trigger pos)

# How to Play
- [W] : move up
- [S] : move down
- [A] : move left
- [D] : move right
- [LMB] : shoot bullet
- [RMB] : special weapon (have cooldown)
- [ESC] : exit the game