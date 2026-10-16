<!DOCTYPE html>
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
