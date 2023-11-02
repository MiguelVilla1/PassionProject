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
    </div>
    <script>
        function openPack() {
            fetch('http://localhost:8281/api/jokes/', { method: 'GET' })
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Network response was not ok');
                    }
                    return response.json();
                })
                .then(player => {
                    // Update the HTML elements with player data
                    document.getElementById('player-name').textContent = player.Name;
                    document.getElementById('player-position').textContent = player.Position;
                    document.getElementById('player-overall').textContent = player.Overall;
                    document.getElementById('player-pace').textContent = player.Pace;
                    document.getElementById('player-shooting').textContent = player.Shooting;
                    document.getElementById('player-passing').textContent = player.Passing;
                    document.getElementById('player-dribbling').textContent = player.Dribbling;
                    document.getElementById('player-defending').textContent = player.Defense;
                    document.getElementById('player-physicality').textContent = player.Physicality;
                })
                .catch(error => {
                    console.error('There was a problem with the fetch operation:', error);
                });
        }
        document.getElementById('open-pack-button').addEventListener('click', openPack);
    </script>
</body>
</html>
