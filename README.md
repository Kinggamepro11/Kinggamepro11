<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Florography: The Language of Flowers</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Florography: The Language of Flowers</h1>
    </header>

    <main>
        <section id="intro">
            <h2>Welcome to the World of Florography</h2>
            <p>Discover the secret meanings behind different flowers and learn how to express yourself through their symbolism.</p>
        </section>

        <section id="flower-list">
            <h2>Explore Flower Meanings</h2>
            <ul>
                <!-- Flower entries will be added here dynamically -->
            </ul>
        </section>

        <section id="search">
            <h2>Search for a Flower</h2>
            <input type="text" id="search-input" placeholder="Enter flower name...">
            <button id="search-button">Search</button>
            <div id="search-results">
                <!-- Search results will be displayed here -->
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Florography</p>
    </footer>

    <script>
        // Array ampliato di fiori con significati
        const flowers = [
            { name: "Rosa", meaning: "Amore e Passione" },
            { name: "Girasole", meaning: "Adorazione e Lealtà" },
            { name: "Tulipano", meaning: "Eleganza e Grazia" },
            { name: "Lavanda", meaning: "Serenità e Devozione" },
            { name: "Orchidea", meaning: "Bellezza Rara" },
            { name: "Margherita", meaning: "Innocenza e Purezza" },
            { name: "Camelia", meaning: "Ammirazione e Perfezione" },
            { name: "Peonia", meaning: "Fortuna e Prosperità" },
            { name: "Gelsomino", meaning: "Amore e Sensualità" },
            { name: "Narciso", meaning: "Nuovi inizi e Rinascita" },
            { name: "Violetta", meaning: "Fedeltà e Umiltà" },
            { name: "Fiore di Loto", meaning: "Purezza e Illuminazione" },
            { name: "Ciclamino", meaning: "Addio e Distacco" },
            { name: "Iris", meaning: "Saggezza e Coraggio" },
            { name: "Dalia", meaning: "Forza e Dignità" },
            { name: "Papavero", meaning: "Riposo e Consolazione" },
            { name: "Magnolia", meaning: "Nobiltà e Perseveranza" },
            { name: "Azalea", meaning: "Moderazione e Abilità" },
            { name: "Fiordaliso", meaning: "Delicatezza e Gentilezza" },
            { name: "Geranio", meaning: "Amicizia e Comfort" },
            { name: "Gardenia", meaning: "Purezza e Dolcezza" },
            { name: "Rododendro", meaning: "Cautela e Pericolo" },
            { name: "Giglio", meaning: "Nobiltà e Devozione" },
            { name: "Viola del Pensiero", meaning: "Ricordo e Amore Segreto" },
            { name: "Primula", meaning: "Gioventù e Nuovo Amore" },
            { name: "Anemone", meaning: "Aspettativa e Perseveranza" },
            { name: "Zinnia", meaning: "Resistenza e Amicizia Duratura" },
            { name: "Fresia", meaning: "Innocenza, fiducia e amicizia" },
            { name: "Mughetto", meaning: "Dolcezza e fortuna" },
            { name: "Garofano", meaning: "Amore e affetto" },
            { name: "Stella alpina", meaning: "Amore e devozione" },
        ];

        const flowerList = document.querySelector('#flower-list ul');
        flowers.forEach(flower => {
            const listItem = document.createElement('li');
            listItem.innerHTML = `<h3>${flower.name}</h3><p>${flower.meaning}</p>`;
            flowerList.appendChild(listItem);
        });

        const searchInput = document.getElementById('search-input');
        const searchButton = document.getElementById('search-button');
        const searchResults = document.getElementById('search-results');

        searchButton.addEventListener('click', () => {
            const searchTerm = searchInput.value.toLowerCase();
            const matchingFlowers = flowers.filter(flower => flower.name.toLowerCase().includes(searchTerm));

            searchResults.innerHTML = ''; // Clear previous results

            if (matchingFlowers.length > 0) {
                matchingFlowers.forEach(flower => {
                    const resultItem = document.createElement('div');
                    resultItem.innerHTML = `<h3>${flower.name}</h3><p>${flower.meaning}</p>`;
                    searchResults.appendChild(resultItem);
                });
            } else {
                searchResults.innerHTML = '<p>No matching flowers found.</p>';
            }
        });
    </script>
</body>
</html>
