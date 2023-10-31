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
<<<<<<< HEAD
        <p>Defending: <span id="player-defending"></span></p>
        <p>Physicality: <span id="player-physicality"></span></p>
        <!-- Add more player attributes here -->
=======
        <p>Defense: <span id="player-defense"></span></p>
        <p>Physicality: <span id="player-physicality"></span></p>
>>>>>>> 852ea7f (api endpoint update)
    </div>
    <script>
        function openPack() {
            fetch('http://localhost:8282/api/open_pack') 
                .then(response => response.json())
                .then(data => {
                    document.getElementById('player-name').textContent = data.name;
                    document.getElementById('player-position').textContent = data.position;
                    document.getElementById('player-overall').textContent = data.overall;
                    document.getElementById('player-pace').textContent = data.pace;
                    document.getElementById('player-shooting').textContent = data.shooting;
                    document.getElementById('player-passing').textContent = data.passing;
                    document.getElementById('player-dribbling').textContent = data.dribbling;
<<<<<<< HEAD
                    document.getElementById('player-defending').textContent = data.defending;
                    document.getElementById('player-physicality').textContent = data.physicality;
                    // Add more lines to display other player attributes
=======
                    document.getElementById('player-defense').textContent = data.defense;
                    document.getElementById('player-physicality').textContent = data.physicality;
>>>>>>> 852ea7f (api endpoint update)
                });
        }
        document.getElementById("open-pack-button").addEventListener("click", openPack);
    </script>
</body>
</html>
