<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>San Valentín</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: Arial, sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            height: 100vh;
            background: url('https://source.unsplash.com/1600x900/?hearts,flowers,love') no-repeat center center/cover;
            text-align: center;
            color: white;
        }
        .content {
            background: rgba(0, 0, 0, 0.6);
            padding: 20px;
            border-radius: 10px;
        }
        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        .buttons {
            display: flex;
            gap: 20px;
            margin-top: 20px;
        }
        button {
            font-size: 1.2rem;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .yes {
            background: #ff4081;
            color: white;
            transition: all 0.3s ease;
        }
        .no {
            background: #6200ea;
            color: white;
        }
        .bear {
            width: 150px;
            height: auto;
            animation: blink 1s infinite alternate;
        }
        @keyframes blink {
            0% { transform: scale(1); }
            100% { transform: scale(1.1); }
        }
    </style>
</head>
<body>
    <audio autoplay loop>
        <source src="https://www.mboxdrive.com/Camila-TodoCambio.mp3" type="audio/mp3">
    </audio>
    <div class="content">
        <h1 id="question">¿Quieres ser mi San Valentín, Weny?</h1>
        <img id="loveImage" src="https://source.unsplash.com/400x300/?love,romance" alt="Imagen de amor">
        <img src="https://www.animatedimages.org/data/media/710/animated-teddy-bear-image-0112.gif" alt="Osito" class="bear">
        <div class="buttons">
            <button class="yes" id="yesButton" onclick="acceptLove()">Sí</button>
            <button class="no" onclick="rejectLove()">No</button>
        </div>
    </div>

    <script>
        const messages = [
            "¿Seguro que no? 🥺", "Piénsalo bien, mi amor 💖", "Sin ti, mi mundo no es lo mismo 😢", "Eres mi todo 💕", "Dame una oportunidad 💓"
        ];
        let index = 0;
        let yesButton = document.getElementById("yesButton");

        function rejectLove() {
            document.getElementById("question").textContent = messages[index];
            document.getElementById("loveImage").src = `https://source.unsplash.com/400x300/?love,romance,${index}`;
            index = (index + 1) % messages.length;
            yesButton.style.fontSize = (parseFloat(getComputedStyle(yesButton).fontSize) + 5) + "px";
            yesButton.style.padding = (parseFloat(getComputedStyle(yesButton).padding) + 5) + "px";
        }

        function acceptLove() {
            alert("¡Sabía que dirías que sí! 💖😍");
        }
    </script>
</body>
</html>

