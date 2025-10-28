<!DOCTYPE html>
<html lang="en">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,intial-scale=1.0">
    <title> Countdown to Happy New Year's</title>
    <link rel="stylesheet" href="">
<body>

    <h1>Countdown to New Year's</h1>
    <div id="countdown" class="countdown"></div>
    <div id="NewYearMessage" class="new-year-message">Happy New Year!</div>

<!-- Java script to countdown -->
    <script>
        // Set the target date for the countdown (January 1, 2025 at midnight)
        const targetDate = new Date('January 1, 2025 00:00:00').getTime();

        // Update the countdown every second
        const countdownTimer = setInterval(function() {
            const now = new Date().getTime();
            const timeLeft = targetDate - now;

            // Calculate time components
            const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            // Display the countdown
            document.getElementById("countdown").innerHTML= `${days}d ${hours}h ${minutes}m ${seconds}`;

            // If the countdown reaches zero, show the New Year message
            if (timeLeft < 0) {
                clearInterval(countdownTimer);
                document.getElementById("countdown").style.display = "none";
                document.getElementById("NewYearMessage").style.display = "block";
            }
        }, interval);
    </script>
</body>
</html>
