<html>
<head>
    <title>Pack Opening</title>
</head>
<style>
    body {
        background-image: url('https://i.ytimg.com/vi/vpjWI1e0Mbk/maxresdefault.jpg');
        background-size: cover;
        background-repeat: no-repeat;
        text-align: center;
    }
</style>
<body>
    <button id="open-pack-button">Open a pack</button>
    <div>
        <h2>Player Stats</h2>
        <p>Name: <span id="player-name"></span></p>
        <p>Position: <span id="player-position"></span></p>
        <p>Overall: <span id="player-overall"></span></p>
        <p>Pace: <span id="player-pace"></span></p>
        <p>Shooting: <span id="player-shooting"></span></p>
        <p>Passing: <span id="player-passing"></span></p>
        <p>Dribbling: <span id="player-dribbling"></span></p>
        <p>Defending: <span id="player-defending"></span></p>
        <p>Physicality: <span id="player-physicality"></span></p>
        <!-- Add more player attributes here -->
    </div>
    <script>
        // Function to request data from the backend
        function openPack() {
            fetch('/api/open_pack')  // Replace '/api/open_pack' with the actual endpoint on your Flask server
                .then(response => response.json())
                .then(data => {
                    // Process and display the data in your HTML
                    document.getElementById('player-name').textContent = data.name;
                    document.getElementById('player-position').textContent = data.position;
                    document.getElementById('player-overall').textContent = data.overall;
                    document.getElementById('player-pace').textContent = data.pace;
                    document.getElementById('player-shooting').textContent = data.shooting;
                    document.getElementById('player-passing').textContent = data.passing;
                    document.getElementById('player-dribbling').textContent = data.dribbling;
                    document.getElementById('player-defending').textContent = data.defending;
                    document.getElementById('player-physicality').textContent = data.physicality;
                    // Add more lines to display other player attributes
                });
        }
        // Add a click event listener to the "Open a pack" button
        document.getElementById("open-pack-button").addEventListener("click", openPack);
    </script>
</body>
</html>
