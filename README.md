<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Etničko Istraživanje</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            margin: 50px;
        }

        #container {
            max-width: 600px;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color: #333;
        }

        p {
            color: #666;
        }

        .radio-group {
            margin-top: 20px;
        }

        .radio-group label {
            display: block;
            margin-bottom: 10px;
        }

        button {
            background-color: #007bff;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
    </style>
    <script>
        function postaviPitanje() {
            var odgovor = document.querySelector('input[name="etnicnost"]:checked');

            if (odgovor) {
                var linkovi = generirajNasumicneLinkove(odgovor.value.toLowerCase());
                if (linkovi.length > 0) {
                    var odabraniLink = linkovi[Math.floor(Math.random() * linkovi.length)];
                    window.location.href = odabraniLink;
                } else {
                    alert('Nepoznata etnička pripadnost.');
                }
            } else {
                alert('Molimo odaberite svoju etničku pripadnost.');
            }
        }

        function generirajNasumicneLinkove(etnicitet) {
            if (etnicitet === 'bosnjak') {
                return shuffle([
                    'https://docs.google.com/forms/d/e/1FAIpQLSed-QEkF3t44P3_UeqizNrgj6oXZ25bgkQhsTBT-DAUPa0OtQ/viewform?usp=sf_link',
                    'https://docs.google.com/forms/d/e/1FAIpQLSfBvKtYYTsxpYRhRIJV4_dlEpD53Txj5yu-BKzK_jHyJu4lXg/viewform?usp=sf_link',
                    'https://docs.google.com/forms/d/e/1FAIpQLSe2NTW2ik8GI2p9yKfsjrKzrd03C6CKMf7_-jUrDgNxO1D8gw/viewform?usp=sf_link',
                    'https://docs.google.com/forms/d/e/1FAIpQLSdKAoR3EUsHA-LUFN20A6eC8xiREiUCHNgVy4zKJ5z2IOn8mw/viewform?usp=sf_link'
                ]);
            } else if (etnicitet === 'srbin') {
                return shuffle([
                    'https://docs.google.com/forms/d/e/1FAIpQLScNPw5Vo-yGGVh4fl0zFCrAqTE_r61k5LaNZnDGU5G2_esbOg/viewform?usp=sf_link',
                    'https://docs.google.com/forms/d/e/1FAIpQLSeyU2AN00Ez1i8OQTfhQzbgInAwQ-l7wBTvrnBlE0yrWa68Nw/viewform?usp=sf_link',
                    'https://docs.google.com/forms/d/e/1FAIpQLSdRe3ENaK7uwo-UzabP5jG51l5eMn5U455qYpWGRRaNZnW-Ag/viewform?usp=sf_link',
                    'https://docs.google.com/forms/d/e/1FAIpQLSeaMU1Sm5sXoWw6s2Z-26tk-PPS0TRWyiqiuuQQcV9v5zloZg/viewform?usp=sf_link'
                ]);
            } else {
                return [];
            }
        }

        function shuffle(array) {
            var currentIndex = array.length, randomIndex;

            while (currentIndex != 0) {
                randomIndex = Math.floor(Math.random() * currentIndex);
                currentIndex--;

                [array[currentIndex], array[randomIndex]] = [array[randomIndex], array[currentIndex]];
            }

            return array;
        }
    </script>
</head>
<body>
    <div id="container">
        <h1>Dobrodošli u istraživanje o Determinantama međugrupnih odnosa Bošnjaka i Srba.</h1>
        <p>Ovo istraživanje provodi se isključivo među Bošnjacima i Srbima, kako bismo bolje razumjeli vaše stavove, percepcije i iskustva vezana uz odnose između vaših dviju zajednica. Ako se identificirate i izjašnjavate kao Bošnjak ili Srbin, pozivamo vas da sudjelujete i podijelite svoje stavove i iskustva. Molimo vas da odaberete svoju etničku pripadnost kako biste nastavili sa istraživanjem (u nastavku ćete dobiti detaljne upute).</p>
        <div class="radio-group">
            <label>
                <input type="radio" name="etnicnost" value="bosnjak">
                Bošnjak
            </label>
            <label>
                <input type="radio" name="etnicnost" value="srbin">
                Srbin
            </label>
        </div>
        <button onclick="postaviPitanje()">Odaberi etničku pripadnost</button>
    </div>
</body>
</html>
