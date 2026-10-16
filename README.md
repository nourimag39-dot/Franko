
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CEG Franco-Arabe Wacha</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

<header>
    <div class="logo">
        <span>🏫</span>
        <div>
            <h1>CEG Franco-Arabe</h1>
            <p>Wacha</p>
        </div>
    </div>

    <nav>
        <a href="#accueil">Accueil</a>
        <a href="#inscription">Inscription</a>
        <a href="#connexion">Connexion</a>
    </nav>
</header>

<section id="accueil" class="hero">
    <div>
        <h2>Bienvenue au CEG Franco-Arabe Wacha</h2>
        <p>
            Plateforme numérique de gestion des élèves,
            des notes et des bulletins scolaires.
        </p>

        <button onclick="afficherInscription()">
            Inscrire un élève
        </button>
    </div>
</section>

<section id="inscription" class="section">
    <h2>Inscription d'un élève</h2>

    <form id="formInscription">

        <label>Nom</label>
        <input type="text" id="nom" placeholder="Nom de l'élève" required>

        <label>Prénom</label>
        <input type="text" id="prenom" placeholder="Prénom de l'élève" required>

        <label>Classe</label>
        <select id="classe" required>
            <option value="">Choisir une classe</option>
            <option value="6e">6e</option>
            <option value="5e">5e</option>
            <option value="4e">4e</option>
            <option value="3e">3e</option>
        </select>

        <label>Téléphone</label>
        <input type="tel" id="telephone" placeholder="Téléphone">

        <label>Mot de passe</label>
        <input type="password" id="password" placeholder="Mot de passe" required>

        <button type="submit">Créer le compte</button>
    </form>

    <p id="message"></p>
</section>

<section id="connexion" class="section connexion">
    <h2>Connexion</h2>

    <form id="formConnexion">

        <label>Identifiant</label>
        <input
            type="text"
            id="identifiant"
            placeholder="Nom ou identifiant"
            required
        >

        <label>Mot de passe</label>
        <input
            type="password"
            id="motDePasse"
            placeholder="Mot de passe"
            required
        >

        <button type="submit">Se connecter</button>
    </form>

    <p id="connexionMessage"></p>
</section>

<section id="espaceEleve" class="dashboard hidden">

    <h2>Espace Élève</h2>

    <div class="card">
        <h3>Informations de l'élève</h3>

        <p><strong>Nom :</strong> <span id="eleveNom"></span></p>
        <p><strong>Prénom :</strong> <span id="elevePrenom"></span></p>
        <p><strong>Classe :</strong> <span id="eleveClasse"></span></p>
    </div>

    <div class="card">
        <h3>Mes notes</h3>

        <table>
            <thead>
                <tr>
                    <th>Matière</th>
                    <th>Note /20</th>
                </tr>
            </thead>

            <tbody id="tableNotes">
            </tbody>
        </table>
    </div>

    <button onclick="deconnexion()">Déconnexion</button>
</section>

<footer>
    <p>© 2026 CEG Franco-Arabe Wacha</p>
</footer>

<script src="script.js"></script>

</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: #f4f7f9;
    color: #222;
}

header {
    background: #075e54;
    color: white;
    padding: 15px 6%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
}

.logo {
    display: flex;
    align-items: center;
    gap: 10px;
}

.logo span {
    font-size: 40px;
}

.logo h1 {
    font-size: 21px;
}

.logo p {
    font-size: 14px;
}

nav {
    display: flex;
    gap: 20px;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.hero {
    min-height: 420px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
    background: linear-gradient(
        135deg,
        #075e54,
        #128c7e
    );
    color: white;
}

.hero h2 {
    font-size: 38px;
    margin-bottom: 15px;
}

.hero p {
    font-size: 18px;
    max-width: 650px;
    margin: auto;
    line-height: 1.6;
}

button {
    margin-top: 20px;
    padding: 12px 25px;
    border: none;
    border-radius: 8px;
    background: #f4b400;
    color: #111;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    opacity: 0.85;
}

.section {
    max-width: 600px;
    margin: 50px auto;
    padding: 30px;
    background: white;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.08);
}

.section h2 {
    text-align: center;
    margin-bottom: 25px;
    color: #075e54;
}

form {
    display: flex;
    flex-direction: column;
}

label {
    margin-top: 12px;
    margin-bottom: 5px;
    font-weight: bold;
}

input,
select {
    padding: 13px;
    border: 1px solid #ccc;
    border-radius: 7px;
    font-size: 15px;
}

input:focus,
select:focus {
    outline: none;
    border-color: #075e54;
}

#message,
#connexionMessage {
    margin-top: 15px;
    text-align: center;
    font-weight: bold;
}

.dashboard {
    max-width: 900px;
    margin: 50px auto;
    padding: 20px;
}

.dashboard h2 {
    color: #075e54;
    text-align: center;
    margin-bottom: 25px;
}

.card {
    background: white;
    padding: 25px;
    margin-bottom: 20px;
    border-radius: 10px;
    box-shadow: 0 3px 12px rgba(0,0,0,0.08);
}

.card h3 {
    color: #075e54;
    margin-bottom: 15px;
}

table {
    width: 100%;
    border-collapse: collapse;
}

th,
td {
    padding: 12px;
    border-bottom: 1px solid #ddd;
    text-align: left;
}

th {
    background: #075e54;
    color: white;
}

.hidden {
    display: none;
}

footer {
    background: #075e54;
    color: white;
    text-align: center;
    padding: 20px;
    margin-top: 50px;
}

@media (max-width: 700px) {

    header {
        flex-direction: column;
        gap: 15px;
    }

    nav {
        gap: 10px;
        flex-wrap: wrap;
        justify-content: center;
    }

    .hero h2 {
        font-size: 28px;
    }

    .section {
        margin: 25px 15px;
        padding: 20px;
    }

    .dashboard {
        margin: 25px 10px;
    }
}
// Inscription
document.getElementById("formInscription").addEventListener("submit", function(e) {

    e.preventDefault();

    const nom = document.getElementById("nom").value;
    const prenom = document.getElementById("prenom").value;
    const classe = document.getElementById("classe").value;
    const telephone = document.getElementById("telephone").value;
    const password = document.getElementById("password").value;

    const eleve = {
        nom: nom,
        prenom: prenom,
        classe: classe,
        telephone: telephone,
        password: password,

        notes: {
            "FR": 0,
            "AR": 0,
            "HG": 0,
            "PC": 0,
            "MT": 0,
            "EPS": 0,
            "EI": 0,
            "SVT": 0,
            "CONDUITE": 0
        }
    };

    localStorage.setItem("eleve", JSON.stringify(eleve));

    document.getElementById("message").textContent =
        "✅ Inscription réussie ! Vous pouvez maintenant vous connecter.";

    document.getElementById("formInscription").reset();
});


// Connexion
document.getElementById("formConnexion").addEventListener("submit", function(e) {

    e.preventDefault();

    const identifiant =
        document.getElementById("identifiant").value;

    const motDePasse =
        document.getElementById("motDePasse").value;

    const eleve = JSON.parse(localStorage.getItem("eleve"));

    if (!eleve) {
        document.getElementById("connexionMessage").textContent =
            "❌ Aucun élève inscrit.";
        return;
    }

    if (
        (identifiant === eleve.nom ||
         identifiant === eleve.prenom) &&
        motDePasse === eleve.password
    ) {

        afficherEspaceEleve(eleve);

        document.getElementById("connexionMessage").textContent =
            "";

    } else {

        document.getElementById("connexionMessage").textContent =
            "❌ Identifiant ou mot de passe incorrect.";
    }
});


// Afficher l'espace élève
function afficherEspaceEleve(eleve) {

    document
        .getElementById("espaceEleve")
        .classList.remove("hidden");

    document.getElementById("eleveNom").textContent =
        eleve.nom;

    document.getElementById("elevePrenom").textContent =
        eleve.prenom;

    document.getElementById("eleveClasse").textContent =
        eleve.classe;

    const table = document.getElementById("tableNotes");

    table.innerHTML = "";

    for (const matiere in eleve.notes) {

        const ligne = document.createElement("tr");

        ligne.innerHTML = `
            <td>${matiere}</td>
            <td>${eleve.notes[matiere]} / 20</td>
        `;

        table.appendChild(ligne);
    }

    document
        .getElementById("espaceEleve")
        .scrollIntoView({
            behavior: "smooth"
        });
}


// Aller vers inscription
function afficherInscription() {

    document
        .getElementById("inscription")
        .scrollIntoView({
            behavior: "smooth"
        });
}


// Déconnexion
function deconnexion() {

    document
        .getElementById("espaceEleve")
        .classList.add("hidden");

    document
        .getElementById("connexion")
        .scrollIntoView({
            behavior: "smooth"
        });
}
