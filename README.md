<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be Jungkook's Valentine!</title>
    <style>
        /* Use provided GIF as background and ensure it loops */
        body {
            position: relative;
            overflow: hidden;
            background: url('https://i.pinimg.com/originals/fe/ab/28/feab2838efa7d30e139e3428e5d48fe2.gif') center/cover no-repeat;
            background-color: #f5c6cb; /* soft pink background */
            background-size: 60%; /* Make Snoopy smaller */
            height: 100vh;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: "Times New Roman", serif;
        }

        /* Centered container for text and buttons */
        .container {
            text-align: center;
            color: red; /* Text color changed to red for the second part */
            font-size: 40px;
            font-weight: bold;
            background: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            position: absolute;
            top: 50%; /* Centered vertically */
            transform: translateY(-50%); /* Correct for exact center */
        }

        /* First part of text in red */
        .blackText {
            color: red; /* First part of the text in red */
        }

        /* Button styles */
        .button {
            font-size: 25px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            font-family: "Times New Roman", serif;
        }

        #yesButton {
            background-color: pink;
            color: red;
        }

        #noButton {
            background-color: red;
            color: white;
            position: absolute;
            font-size: 25px;
        }

        /* Pink Hearts */
        .heart {
            position: absolute;
            font-size: 40px;
            color: pink;
            animation: fall 2s linear infinite;
        }

        @keyframes fall {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }

        /* Ending message */
        .endMessage {
            display: none;
            font-size: 30px; /* Smaller font size */
            font-weight: bold;
            text-align: center;
            color: black;
        }
    </style>
</head>
<body>

    <!-- Background Music -->
    <audio autoplay loop>
        <source src="https://www.youtube.com/watch?v=KvLdn_HkU0Y" type="audio/mpeg">
    </audio>

    <div class="container" id="question">
        <span class="blackText">Be </span>Jungkook's Valentine!  
        <br>
        <button class="button" id="yesButton" onclick="acceptLove()">Yes</button>
        <button class="button" id="noButton" onclick="moveNo()">No</button>
    </div>

    <div class="endMessage" id="endMessage">  
        Hehe, thank you, my beautiful paipai <3  
    </div>

    <script>
        let noButton = document.getElementById("noButton");
        let question = document.getElementById("question");
        let endMessage = document.getElementById("endMessage");

        function acceptLove() {
            question.style.display = "none"; 
            endMessage.style.display = "block"; 
        }

        function moveNo() {
            // Generate random position every time the button is clicked
            const x = Math.random() * (window.innerWidth - 100);
            const y = Math.random() * (window.innerHeight - 50);
            noButton.style.left = `${x}px`;
            noButton.style.top = `${y}px`;
        }

        function createHearts() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "💖";
            heart.style.left = Math.random() * window.innerWidth + "px";
            heart.style.top = window.innerHeight + "px";
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 2000);
        }

        setInterval(createHearts, 300);
    </script>

</body>
</html>
