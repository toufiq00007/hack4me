# hack4me


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Cheat Code Example</title>
    <style>
        body {
            font-family: sans-serif;
            text-align: center;
            padding-top: 50px;
        }
        #secretMessage {
            color: green;
            font-size: 2em;
            display: none; /* Hidden by default */
        }
        #status {
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h1>Try the Cheat Code!</h1>
    <p>The code is: **Up, Up, Down, Down, Left, Right, Left, Right, B, A, Enter**</p>

    <div id="status">Start typing the code anywhere on the page...</div>

    <div id="secretMessage">
        🥳 **CHEAT CODE ACTIVATED! SECRET POWER UNLOCKED!** 🥳
    </div>

    <script>
        // The famous Konami Code sequence of key codes
        const konamiCode = [38, 38, 40, 40, 37, 39, 37, 39, 66, 65, 13];
        let codePosition = 0; // Tracks how far into the code the user is

        // Get the elements we want to modify
        const secretMessage = document.getElementById('secretMessage');
        const statusDiv = document.getElementById('status');

        document.addEventListener('keydown', function(e) {
            // e.keyCode gets the numerical code for the pressed key
            const requiredKey = konamiCode[codePosition];

            if (e.keyCode === requiredKey) {
                // Correct key pressed! Move to the next position in the code
                codePosition++;
                statusDiv.textContent = `Correct key! Progress: ${codePosition}/${konamiCode.length}`;

                // Check if the entire code has been entered
                if (codePosition === konamiCode.length) {
                    // Code complete! Trigger the "cheat"
                    secretMessage.style.display = 'block'; // Show the secret message
                    statusDiv.textContent = `CODE SUCCESSFUL!`;
                    
                    // Reset position after successful entry (optional)
                    codePosition = 0; 
                }
            } else {
                // Wrong key pressed! Reset the progress
                codePosition = 0;
                statusDiv.textContent = 'Oops! Code failed. Start over. (Up, Up, Down, Down, ...)'
            }
        });
    </script>

</body>
</html>
