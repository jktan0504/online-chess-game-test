# Installation Guide
Node version is 16.20.2
```
npm install
npm start
```

# Problem
First of all, set the node version<br>
We will review not only your code optimization but also your coding style and coding speed.<br>
Find the AI ​​monkey part in your React component.<br>
And you should optimize the code in the component.<br>
You don't need to optimize all the functions. It's enough for some special functions.

---
# Solutions by @jktan0504
---
# Optimizations Overview

This project involves 3D scene management using **THREE.js**, and it includes various optimizations for improving performance, readability, and scalability. Below are the key areas that have been optimized.

## 1. Mouse Down Action

### Description:
The **Mouse Down Action** handles user interactions with the 3D scene by detecting mouse clicks on objects. It triggers specific actions based on the item the user is interacting with.

### Optimization:
- Refactored logic to improve code readability and reduce duplication.
- Used event delegation to centralize event handling, ensuring easier maintenance and scalability.
- Optimized the use of raycasting to detect and handle user clicks on the 3D scene objects.

### Benefits:
- Cleaner, more maintainable code.
- Reduced redundancy and better performance due to streamlined event handling.

## 2. Mouse Move Action

### Description:
The **Mouse Move Action** detects mouse movement over the scene, updating visual feedback based on the selected item and interaction.

### Optimization:
- Split complex logic into reusable functions to handle specific items (e.g., `iceWall` and `petrify`).
- Used helper methods to update mouse mesh material colors and positions, reducing code duplication.
- Improved raycasting logic for more accurate intersection detection.

### Benefits:
- Improved performance by limiting the amount of work done during each mouse movement event.
- Better modularity and scalability with smaller, focused methods for handling specific interactions.

## 3. Create SpotLight

### Description:
Spotlights are used in the scene to illuminate specific objects or areas, adding realism and depth.

### Optimization:
- Simplified the creation and configuration of spotlights by consolidating parameters.
- Ensured proper memory management by reusing spotlight objects when possible rather than constantly creating new ones.

### Benefits:
- Efficient spotlight management, reducing computational overhead.
- Improved lighting consistency in the scene with simplified configuration.

## 4. Scene Outline Effect - Composer

### Description:
The **Scene Outline Effect** is used to highlight selected objects in the 3D scene, improving user interaction.

### Optimization:
- Used **THREE.js Composer** to apply post-processing effects, optimizing the scene rendering pipeline.
- Consolidated multiple shader passes into a single pass where possible to reduce GPU overhead.
- Implemented effective caching for frequently used outlines, minimizing unnecessary recalculations.

### Benefits:
- Optimized rendering pipeline with Composer for improved performance.
- Reduced visual glitches and flickering by applying the outline effect more efficiently.

## 5. Windows Resize Handler

### Description:
The **Window Resize Handler** ensures that the 3D scene adjusts correctly when the window size changes.

### Optimization:
- Consolidated resize logic to ensure the renderer and camera are updated only when necessary.
- Applied **debouncing** to the resize handler to prevent excessive recalculations during rapid window resizing.
- Used a more efficient method for updating the aspect ratio and resizing the renderer.

### Benefits:
- More responsive window resizing with minimal performance impact.
- Improved user experience, especially on mobile devices or when resizing the window.

## 6. Socket Connections

### Description:
The **Socket Connections** allow real-time communication with the backend, enabling multiplayer functionality or dynamic scene updates.

### Optimization:
- Implemented connection pooling and proper socket management to reduce the number of open connections.
- Reduced overhead by using optimized event handlers for socket events, ensuring minimal impact on performance.
- Added automatic reconnection logic for more reliable socket communication.

### Benefits:
- Faster and more reliable socket communication.
- Reduced resource consumption by handling socket connections more efficiently.

## 7. Mesh Array

### Description:
The **Mesh Array** is used to store and manage all mesh objects in the 3D scene.

### Optimization:
- Implemented a more efficient data structure for storing meshes, reducing lookup times and memory consumption.
- Used spatial partitioning to speed up raycasting and object interaction checks.
- Ensured proper cleanup of unused meshes to avoid memory leaks.

### Benefits:
- Improved performance when interacting with large numbers of meshes.
- Reduced memory usage and better handling of dynamic scene changes.

## 8. States & Props

### Description:
The **States & Props** represent the dynamic data and configuration of the application, used to manage UI state and scene parameters.

### Optimization:
- Simplified state management by using a more modular approach to store and update state.
- Optimized the way props are passed and updated in the application to prevent unnecessary re-renders.
- Used memoization and efficient state updating techniques to improve performance during state changes.

### Benefits:
- Reduced unnecessary renders and improved performance.
- Better organization and separation of concerns, making the code easier to maintain and extend.

---

### Summary of Benefits

By optimizing these areas, the project has seen significant improvements in:
- **Performance**: Reduced redundant calculations and optimized resource management (e.g., socket connections, resizing, spotlight creation).
- **Code Readability**: More modular and maintainable code due to refactoring and breaking down complex functions.
- **Scalability**: The system is now more adaptable to future changes or additional features without introducing bottlenecks or performance issues.

---
