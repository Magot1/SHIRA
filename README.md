<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dino Game</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="gameContainer">
        <div id="dino"></div>
        <div id="obstacle"></div>
    </div>
    <script src="script.js"></script>
</body>
</html>

body {
    margin: 0;
    padding: 0;
    background-color: #f5f5f5;
}

#gameContainer {
    position: relative;
    width: 600px;
    height: 200px;
    margin: 100px auto;
    border: 1px solid #ccc;
    overflow: hidden;
}

#dino {
    position: absolute;
    bottom: 0;
    left: 50px;
    width: 50px;
    height: 50px;
    background-color: #000;
}

#obstacle {
    position: absolute;
    bottom: 0;
    right: 0;
    width: 20px;
    height: 50px;
    background-color: #000;
}

document.addEventListener('DOMContentLoaded', function() {
    const dino = document.getElementById('dino');
    const obstacle = document.getElementById('obstacle');

    function jump() {
        if (dino.classList != 'jump') {
            dino.classList.add('jump');
            setTimeout(function() {
                dino.classList.remove('jump');
            }, 300);
        }
    }

    document.addEventListener('keydown', function(event) {
        if (event.code === 'Space') {
            jump();
        }
    });

    function checkCollision() {
        const dinoBottom = parseInt(window.getComputedStyle(dino).getPropertyValue('bottom'));
        const obstacleLeft = parseInt(window.getComputedStyle(obstacle).getPropertyValue('left'));
        if (obstacleLeft < 50 && obstacleLeft > 0 && dinoBottom <= 50) {
            alert('Game Over!');
        }
    }

    setInterval(checkCollision, 10);
});
