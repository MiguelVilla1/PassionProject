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
                    // Add more lines to display other player attributes
                });
        }
        // Add a click event listener to the "Open a pack" button
        document.getElementById("open-pack-button").addEventListener("click", openPack);
    </script>
</body>
</html>
