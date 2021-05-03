<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mira esto ♥️</title>
    <link rel="preconnect" href="https://fonts.gstatic.com"> 
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@10"></script>
</head>
<style>
    body {
        background:linear-gradient(135deg, #ffb8e1 0%,#eb1ae6 100%);
        font-family: 'Montserrat', sans-serif;
        padding: 0;
        margin: 0;
    }
    main {
        height: calc(100vh - 50px);
    }
    .container {
        max-width: 400px;
        margin: auto;
    }
    .box {
        margin-top: 50px;
        border: 1px solid black;
        border-radius: 5px;
        text-align: center;
        background: white;
    }
    #pool {
        position: relative;
        height: 80%;
    }
    button {
        background: #BCFFB8;
        border-radius: 0;
        position: absolute;
        border: 1px solid black;
        font-size: 40px;
        border-radius: 15px;
        padding: 10px 20px;
        cursor: pointer;
    }
    button:hover {
        background: #a4e9a0;
    }
    #yes {
        z-index: 999;
    }
    #yes, #no {
        position: absolute;
    }
    img {
        max-width: 100%;
        height: auto;
    }
</style>
<body>
    <main>
        <div class="container">
            <div class="box">
                <h2>Katherine Marcillo, puedes hablar conmigo, por favor :C? ♥️</h2>
                <p id="message"></p>
            </div>
        </div>
        <div id="pool">
            <button id="yes" style="top: 100px;left: 60%;">
                Sí 🥰
            </button>
            <button id="no" style="top: 100px;left: 20%;">
                No, Luis 😒
            </button>
        </div>
    </main>

    <script>
        var yes = document.getElementById('yes');
        var no = document.getElementById('no');
        var messages = [
            '¿Vas a ponerte asi?',
            'Casi',
            'Yo se que quieres 😘',
            'No te hagas rogar',
            'Tranquila, lo entiendo 🙃',
            'Yo se que quieres 😏',
            'Prometo quererte ☺️',
            'Mi amooooooooooooooooooooooooooor 😫',
            'Te doy otra oportunidad 😚',
        ];
        yes.addEventListener('click', showAlert);
        if(window.outerWidth <= 768) {
            no.addEventListener('click', randomPosition); // Compatibilidad para celulares y tablets
        } else {
            no.addEventListener('mouseover', randomPosition);
        }

        function showAlert() {
            Swal.fire({
                title: 'Sabía que dirías que sí, te quiero, Katherine... ♥️',
                html: `
                    <img src="patricio.gif" alt="patricio"/>
                `,
                showConfirmButton: false,
            })
        }

        function randomPosition(element) {
            var pool = document.getElementById('pool');
            var message = document.getElementById('message');
            message.innerText = messages[randomBetween(0, 5)]
            var top = randomBetween(0, pool.offsetHeight - 75, 'vertical') + 'px';
            var left = randomBetween(15, 85, 'horizontal') + '%';
            // console.log('hover', top, left);

            element.target.style['top'] = top;
            element.target.style['left'] = left;
            //console.log(element.target.style['top'], element.target.style['left']);
        }

        function randomBetween(min, max, type) {
            var random = Math.floor(Math.random() * (max - min) + min);
            if(type === 'horizontal') {
                if(random > 42 && random < 76) {
                    return randomBetween(min, max, type);
                }
            }
            return random;
        }
    </script>
</body>
</html>
