# Visual-Studio
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Moments of Reflection: Music & Calm</title>
    <!-- Tailwind CSS for modern styling and responsiveness -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Custom CSS to set the background color and font family */
        body {
            background-color: #e6f7f7; /* A calming, light teal */
            font-family: 'Inter', sans-serif; /* A modern, clean font */
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh; /* Ensure it takes full viewport height */
            margin: 0;
            padding: 20px; /* Add some padding around the content */
            box-sizing: border-box;
        }

        /* Styling for the animation element */
        .animated-box {
            width: 100px;
            height: 100px;
            background-color: #A5D6A7; /* A soft, calming green */
            position: relative;
            border-radius: 12px; /* Rounded corners for aesthetics */
            opacity: 0.8;
            transition: transform 1s ease-in-out, opacity 1s ease-in-out, background-color 1s ease-in-out; /* Smooth transition for animation */
            margin-top: 30px; /* Space above the box */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Subtle shadow */
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-weight: bold;
            text-align: center;
            flex-shrink: 0; /* Prevent shrinking on smaller screens */
        }

        /* Responsive iframe container for YouTube video */
        .video-container {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%; /* 16:9 Aspect Ratio (height / width = 9 / 16 = 0.5625) */
            height: 0;
            overflow: hidden;
            border-radius: 16px; /* Rounded corners for the video container */
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* More prominent shadow */
            max-width: 800px; /* Limit max width for large screens */
            margin-bottom: 30px; /* Space below each video */
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }
    </style>
</head>
<body>

    <h1 class="text-4xl md:text-5xl font-bold text-gray-800 mb-6 text-center">
        A Space for Reflection: Bittersweet Symphony & Weightless
    </h1>

    <p class="text-lg text-gray-600 mb-8 text-center max-w-2xl">
        Welcome to a quiet space where music inspires contemplation. Here, we feature two poignant pieces: the instrumental depths of 'Bittersweet Symphony' and the profound tranquility of 'Weightless.' Allow these melodies to guide your thoughts.
    </p>

    <!-- YouTube Music Video Embed 1: Bittersweet Symphony (Instrumental) -->
    <div class="video-container">
        <iframe
            src="https://www.youtube.com/embed/ELzbYhz5VBo?autoplay=0&mute=0"
            title="YouTube video player - Bittersweet Symphony (Instrumental) (New URL)"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen>
        </iframe>
    </div>

    <!-- YouTube Music Video Embed 2: Weightless by Marconi Union -->
    <div class="video-container">
        <iframe
            src="https://www.youtube.com/embed/sYoqCJNPxv4?autoplay=0&mute=0"
            title="YouTube video player - Weightless by Marconi Union (New URL)"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen>
        </iframe>
    </div>

    <!-- Animated Element -->
    <div id="myAnimatedBox" class="animated-box">
        <p>Finding Serenity</p>
    </div>

    <script>
        // Get the animated box element from the HTML document.
        const animatedBox = document.getElementById('myAnimatedBox');

        // Define a series of reflective messages and coordinating colors for the animated box.
        const messages = [
            { text: 'Deep Reflection', color: '#B0BEC5' },  // A subtle grey for contemplation
            { text: 'Inner Calm', color: '#90CAF9' },      // A gentle blue for tranquility
            { text: 'Finding Serenity', color: '#A5D6A7' } // A calming green for peace
        ];
        let messageIndex = 0; // Initialize the index to cycle through the messages.

        // This function orchestrates the animation and updates the content of the box.
        function animateBox() {
            // Update the text and background color of the animated box based on the current message.
            animatedBox.querySelector('p').textContent = messages[messageIndex].text;
            animatedBox.style.backgroundColor = messages[messageIndex].color;

            // Apply a subtle pulsing visual effect.
            animatedBox.style.transform = 'scale(1.1)'; // Slightly enlarge the box.
            animatedBox.style.opacity = '1';            // Make it fully visible.

            // After a brief delay, return the box to its original size and opacity, completing the pulse.
            setTimeout(() => {
                animatedBox.style.transform = 'scale(1)';   // Revert to original size.
                animatedBox.style.opacity = '0.8';          // Revert to original opacity.
            }, 750); // The pulse animation takes 0.75 seconds.

            // Advance to the next message in the array, looping back to the start if at the end.
            messageIndex = (messageIndex + 1) % messages.length;
        }

        // Set an interval to call the 'animateBox' function every 2 seconds, creating a continuous animation loop.
        setInterval(animateBox, 2000);

        // Call 'animateBox' once immediately upon page load to start the animation without delay.
        animateBox();
    </script>
</body>
</html>

