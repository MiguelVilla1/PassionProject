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
    <button id="random-link-button">Open a pack</button>
    <script>
        // Array of three random URLs
        var randomLinks = [
            'https://cdn.realsport101.com/images/ncavvykf/realsport-production/1da4583eef5fa0540aedd0c1b721da108000b863-612x919.png?w=612&h=919&auto=format',
            'https://media.contentapi.ea.com/content/dam/ea/fifa/fifa-22/news/common/ratings-reveal/fastest-players/kylian-mbappe.png.adapt.crop16x9.652w.png',
            'https://cdn.theathletic.com/app/uploads/2022/09/10053301/Messi_158023-1.png'
        ];
        // Function to open a random URL when the button is clicked
        function openRandomLink() {
            // Generate a random index to select a URL from the array
            var randomIndex = Math.floor(Math.random() * randomLinks.length);
            var randomURL = randomLinks[randomIndex];
            // Open the randomly selected URL in a new tab
            window.open(randomURL, '_blank');
        }
        // Add a click event listener to the button
        document.getElementById("random-link-button").addEventListener("click", openRandomLink);
    </script>
</body>
</html>