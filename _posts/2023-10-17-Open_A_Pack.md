<!DOCTYPE html>
<html>
<head>
    <title>Pack Opening</title>
    <style>
        body {
            background-image: url('https://i.ytimg.com/vi/vpjWI1e0Mbk/maxresdefault.jpg');
            background-size: cover;
            background-repeat: no-repeat;
            text-align: center;
        }
    </style>
</head>
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
            fetch('http://fifabackend.stu.nighthawkcodingsociety.com/') 
                .then(response => response.json())
                .then(data => {
                    document.getElementById('player-name').textContent = data.name;
                    document.getElementById('player-position').textContent = data.pos;
                    document.getElementById('player-overall').textContent = data.ovr;
                    document.getElementById('player-pace').textContent = data.pac;
                    document.getElementById('player-shooting').textContent = data.sho;
                    document.getElementById('player-passing').textContent = data.pas;
                    document.getElementById('player-dribbling').textContent = data.dri;
                    document.getElementById('player-defending').textContent = data.def;
                    document.getElementById('player-physicality').textContent = data.phy;
                });
        }
        document.getElementById("open-pack-button").addEventListener("click", openPack);
    </script>
</body>
</html>
