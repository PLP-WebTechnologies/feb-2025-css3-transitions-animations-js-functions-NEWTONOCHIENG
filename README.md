# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Animation with LocalStorage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Interactive Button Animation</h1>
        <button id="animateButton">Animate Me!</button>
        <div id="box" class="box"></div>
    </div>

    <script src="script.js"></script>
</body>
</html>
/* Basic styling */
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    text-align: center;
    padding: 50px;
}

.container {
    margin: auto;
    width: 50%;
}

button {
    background-color: #3498db;
    color: white;
    padding: 15px 30px;
    border: none;
    cursor: pointer;
    font-size: 18px;
    border-radius: 5px;
    margin: 20px 0;
    transition: transform 0.3s ease;
}

button:hover {
    background-color: #2980b9;
    transform: scale(1.1);
}

/* The box that will be animated */
.box {
    width: 150px;
    height: 150px;
    margin: 20px auto;
    background-color: #e74c3c;
    transition: transform 1s ease, background-color 1s ease;
}

/* Keyframes for smooth animation */
@keyframes bounceAnimation {
    0% {
        transform: translateY(0);
        background-color: #e74c3c;
    }
    50% {
        transform: translateY(-50px);
        background-color: #f39c12;
    }
    100% {
        transform: translateY(0);
        background-color: #e74c3c;
    }
}

.animated {
    animation: bounceAnimation 1s infinite;
}// Get references to the DOM elements
const animateButton = document.getElementById('animateButton');
const box = document.getElementById('box');

// Check if the user has already animated the box
if (localStorage.getItem('hasAnimated') === 'true') {
    box.classList.add('animated');
    animateButton.textContent = 'You Already Animated the Box!';
    animateButton.disabled = true;
}

// Function to trigger animation and store user preference
function triggerAnimation() {
    // Add the animation class to trigger the CSS animation
    box.classList.add('animated');

    // Disable the button after the animation has been triggered
    animateButton.textContent = 'You Already Animated the Box!';
    animateButton.disabled = true;

    // Store the animation state in localStorage
    localStorage.setItem('hasAnimated', 'true');
}

// Add event listener to the button to trigger the animation
animateButton.addEventListener('click', triggerAnimation);
Happy Coding! 💻✨
