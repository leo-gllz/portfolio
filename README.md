# 🚀 Guide de déploiement — Portfolio sur GitHub Pages

## Ce que tu obtiens

Un portfolio HTML/CSS/JS **100% statique**, sans dépendance externe (hormis Google Fonts), prêt à être hébergé gratuitement sur GitHub Pages.

---

## Étape 1 — Créer le dépôt GitHub

1. Connecte-toi sur [github.com](https://github.com)
2. Clique sur **"New repository"**
3. Donne-lui le nom : `ton-username.github.io`
   - **Important** : remplace `ton-username` par **ton vrai nom d'utilisateur GitHub**, exactement comme il apparaît dans l'URL de ton profil
4. Coche **"Public"**
5. Laisse tout le reste par défaut et clique sur **"Create repository"**

> **Exemple** : si ton compte GitHub s'appelle `jdupont`, le dépôt doit s'appeler `jdupont.github.io` — et ton site sera accessible à `https://jdupont.github.io`

---

## Étape 2 — Préparer tes fichiers

Structure recommandée dans ton dépôt :

```
ton-username.github.io/
├── index.html          ← le fichier principal (celui que tu as reçu)
├── assets/             ← ton dossier pour les médias
│   ├── photo.jpg       ← ta photo de profil
│   ├── projet1.png     ← captures d'écran de tes projets
│   └── favicon.ico     ← icône de l'onglet (optionnel)
└── README.md           ← ce guide (optionnel dans le dépôt)
```

---

## Étape 3 — Personnaliser avant de publier

Ouvre `index.html` dans ton éditeur de code (VS Code recommandé) et modifie les éléments marqués par des commentaires `<!-- ─── modifie ici ─── -->` :

| Quoi | Où chercher |
|---|---|
| Ton nom complet | `<title>`, `.nav-logo`, `hero-name`, `footer-txt` |
| Ton titre / rôle | `.hero-role` |
| Ta bio | `.hero-bio`, les `<p>` dans `#about` |
| Ta photo | `.about-photo-frame` (voir instructions dans le HTML) |
| Tes statistiques | `data-count="X"` et les labels `.stat-lbl` |
| Tes compétences | Les blocs `.skill-cat` |
| Tes projets | Les blocs `.project-card` |
| Ton email | `.contact-mail` (href et texte) |
| Tes réseaux | Les `.social-btn` dans `#contact` |

### Ajouter ta photo

1. Place ton image dans `assets/photo.jpg`
2. Dans `index.html`, trouve le commentaire `POUR AJOUTER TA PHOTO`
3. Remplace le contenu du `<div class="about-photo-frame">` par :
   ```html
   <img src="assets/photo.jpg" alt="Photo de Ton Nom"
        style="width:100%;height:100%;object-fit:cover;">
   ```

### Choisir ton thème définitivement

1. Ouvre le site localement et utilise le bouton 🎨 en bas à droite pour tester les 5 thèmes
2. Une fois ton choix fait, dans le `<html>` tout en haut du fichier, garde uniquement le thème choisi :
   ```html
   <html lang="fr" data-theme="void">
   <!-- Remplace "void" par : arctic | terminal | ember | slate -->
   ```
3. Dans le CSS, **supprime les 4 autres blocs de thème** (non obligatoire mais allège le fichier)
4. **Supprime le bloc `THEME SWITCHER`** (HTML + CSS) pour ne pas l'afficher en production

---

## Étape 4 — Publier sur GitHub Pages

### Méthode A — Via l'interface web (recommandée pour débuter)

1. Glisse-dépose tes fichiers directement sur la page du dépôt GitHub
2. Va dans **Settings** → **Pages** (dans le menu de gauche)
3. Dans "Source", sélectionne **"Deploy from a branch"**
4. Choisis la branche **`main`**, dossier **`/ (root)`**
5. Clique sur **Save**

Ton site sera en ligne en **1 à 2 minutes** à l'adresse :
`https://ton-username.github.io`

---

### Méthode B — Via Git en ligne de commande

```bash
# Clone le dépôt que tu viens de créer
git clone https://github.com/ton-username/ton-username.github.io
cd ton-username.github.io

# Copie tes fichiers dans ce dossier, puis :
git add .
git commit -m "Initial portfolio"
git push origin main
```

GitHub Pages se déploie automatiquement à chaque `git push`.

---

## Étape 5 (optionnel) — Nom de domaine personnalisé

Si tu veux utiliser `www.tonnom.fr` à la place de `ton-username.github.io` :

1. Achète un domaine chez OVH, Namecheap, Cloudflare, etc.
2. Dans le DNS de ton domaine, ajoute un enregistrement **CNAME** :
   ```
   www  →  ton-username.github.io
   ```
3. Dans GitHub → Settings → Pages → "Custom domain", entre `www.tonnom.fr`
4. Coche **"Enforce HTTPS"**

---

## Mettre à jour le site

À chaque modification :

```bash
git add .
git commit -m "Mise à jour : nouveau projet / changement de photo / etc."
git push origin main
```

Le site se met à jour automatiquement en quelques secondes.

---

## Résolution de problèmes courants

| Problème | Solution |
|---|---|
| Le site ne s'affiche pas | Vérifie que le fichier s'appelle exactement `index.html` (minuscules) |
| Les images n'apparaissent pas | Vérifie les chemins : `assets/photo.jpg` (sensible à la casse) |
| Les polices ne chargent pas | Vérifie ta connexion internet — Google Fonts nécessite internet |
| Le site affiche l'ancien contenu | Vide le cache du navigateur (Ctrl+Shift+R) |
| Erreur 404 | Attends 2 min et réessaie — le déploiement peut prendre un peu de temps |

---

## Checklist avant mise en ligne

- [ ] Remplacé `[Ton Nom]` partout dans le HTML
- [ ] Ajouté ma photo ou supprimé le placeholder
- [ ] Rempli les sections About, Skills, Projects, Contact
- [ ] Mis mes vrais liens GitHub et LinkedIn
- [ ] Mis mon vrai email
- [ ] Choisi mon thème définitif (et éventuellement supprimé le switcher)
- [ ] Testé sur mobile et sur desktop
- [ ] Vérifié tous les liens (projets, réseaux...)

---

*Bon courage ! 🎉*
