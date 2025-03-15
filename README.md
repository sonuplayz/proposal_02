<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Heartbreak Proposal Animation</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #fffcf2; /* Soft background color */
            overflow: hidden;
        }

        #scene {
            position: relative;
            text-align: center;
        }

        #heart {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100px;
            height: 100px;
            background: red;
            clip-path: polygon(50% 0%, 100% 35%, 100% 85%, 50% 100%, 0% 85%, 0% 35%);
            animation: heartbeat 1s infinite;
        }

        @keyframes heartbeat {
            0% {
                transform: scale(1);
            }
            25% {
                transform: scale(1.2);
            }
            50% {
                transform: scale(1);
            }
        }

        #noButton {
            position: absolute;
            bottom: 20px;
            padding: 10px 20px;
            font-size: 20px;
            cursor: pointer;
            background-color: red;
            color: white;
            border: none;
            border-radius: 5px;
        }

    </style>
</head>
<body>
    <div id="scene">
        <div id="proposal">
            <div id="person">
                <!-- You can add an image of the person proposing if you like -->
                <img src="https://via.placeholder.com/150" alt="Person" />
            </div>
            <div id="heart"></div>
            <button id="noButton">She said No...</button>
        </div>
    </div>

    <script>
        document.getElementById('noButton').addEventListener('click', () => {
            // Trigger heartbreak animation
            const heart = document.getElementById('heart');

            // Remove the heartbeat animation
            heart.style.animation = 'none';
            
            // Make the heart break
            heart.style.transform = 'scale(0)';
            
            // Add a "shattered" effect (fading out the heart)
            heart.style.transition = 'transform 0.5s ease, opacity 0.5s ease';
            setTimeout(() => {
                heart.style.opacity = '0'; // Fading the heart
            }, 500);

            // Optionally, change the background color to reflect the sadness
            document.body.style.backgroundColor = '#6e6e6e'; // Gray background
        });
    </script>
</body>
</html>
