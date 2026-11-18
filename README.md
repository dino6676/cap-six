# Cap Six · mode d'emploi

**Cap Six** est ton plan de rattrapage PrEP sous forme d'appli : planning jour par jour jusqu'aux examens blancs du 4 janvier, suivi de progression, minuteur de concentration, suivi des lectures, échéances et méthodes. Le nom vient de l'objectif : **6/6 dans chaque épreuve**, et garder le cap.

---

## 1. Ai-je besoin de GitHub ?

**Non, pas pour utiliser l'appli.** Il existe deux versions, avec exactement le même contenu :

| | **Version Claude** (déjà prête) | **Version installée** (ce dépôt GitHub) |
|---|---|---|
| Adresse | ton lien `claude.ai/artifact/…` | `https://TON-PSEUDO.github.io/cap-six/` |
| Mac + iPhone | oui, dans le navigateur ou en raccourci | oui, comme une vraie appli (icône, plein écran) |
| Synchro Mac ↔ iPhone | automatique (ton compte Claude) | avec un token GitHub (étape 4) |
| Hors connexion | non | oui |
| Modifiée par Claude | directement depuis la conversation | Claude pousse le code si GitHub est relié à Claude, sinon tu remplaces un fichier |
| Compte nécessaire | Claude | Claude + GitHub (gratuit) |

**Mon conseil** : utilise la version Claude dès maintenant (2 minutes, section 2). Fais la version installée (section 3) quand tu as 15 minutes, si tu veux une vraie icône d'appli et le mode hors ligne.

> ⚠️ Les deux versions ne partagent pas leurs cases cochées : la version Claude garde ta progression dans ton compte Claude, la version installée dans GitHub. Choisis-en une comme version principale. Pour passer de l'une à l'autre : **Réglages & aide → Copier ma progression**, puis **Importer** dans l'autre.

---

## 2. Version Claude : l'installer sur iPhone et Mac (2 min)

**iPhone**
1. Ouvre ton lien d'appli dans **Safari** (pas dans l'appli Claude).
2. Connecte-toi à Claude si on te le demande.
3. Bouton **Partager** (carré avec une flèche) → **Sur l'écran d'accueil** → **Ajouter**.

**Mac**
1. Ouvre le lien dans **Safari**.
2. Menu **Fichier → Ajouter au Dock** (macOS 14 Sonoma ou plus récent).
   Avec Chrome : menu **⋮ → Caster, enregistrer et partager → Installer la page en tant qu'application**.

La progression se synchronise toute seule entre tes appareils.

---

## 3. Version installée : ta propre appli sur GitHub (15 min)

### Étape 1 · Créer un compte GitHub
Va sur **github.com/signup**. Choisis un pseudo simple : il apparaîtra dans l'adresse de ton appli.

### Étape 2 · Créer le dépôt
1. Sur github.com, bouton **+** en haut à droite → **New repository**.
2. **Repository name** : `cap-six`
3. Coche **Public** (GitHub Pages est gratuit pour les dépôts publics).
4. Ne coche rien d'autre (pas de README, on a déjà le nôtre) → **Create repository**.

> Le dépôt public contient le planning, pas tes cases cochées ni tes notes : elles restent sur ton appareil, ou dans un Gist secret si tu actives la synchro.

### Étape 3 · Mettre les fichiers en ligne
Deux possibilités.

**A. Laisser Claude le faire (recommandé)**
1. Dans les **réglages de claude.ai**, section des connecteurs, **connecte GitHub** et autorise l'accès au dépôt `cap-six`.
2. Reviens dans la conversation et écris : *« GitHub est connecté, pousse Cap Six dans mon dépôt TON-PSEUDO/cap-six »*.

**B. À la main, depuis le Mac**
1. Décompresse `cap-six.zip`.
2. Sur la page de ton dépôt vide, clique sur **uploading an existing file**.
3. Ouvre le dossier `cap-six` et **glisse tout son contenu** (les fichiers **et** le dossier `icons`) dans la page. Utilise **Chrome** : Safari ne transfère pas toujours les dossiers.
4. En bas, **Commit changes**.

Contenu attendu dans le dépôt :
```
index.html
manifest.webmanifest
sw.js
README.md
icons/apple-touch-icon.png
icons/icon-192.png
icons/icon-512.png
icons/icon-maskable-512.png
```

Si tu préfères le Terminal :
```bash
cd ~/Downloads/cap-six
git init
git add .
git commit -m "Cap Six v1"
git branch -M main
git remote add origin https://github.com/TON-PSEUDO/cap-six.git
git push -u origin main
```
(Git demandera ton pseudo et, comme mot de passe, un token GitHub avec le droit `repo`.)

### Étape 4 · Publier l'appli (GitHub Pages)
1. Dans ton dépôt : **Settings** → **Pages** (menu de gauche).
2. **Build and deployment → Source** : `Deploy from a branch`.
3. **Branch** : `main`, dossier `/ (root)` → **Save**.
4. Attends 1 à 2 minutes et recharge : l'adresse apparaît en haut, du type
   **`https://TON-PSEUDO.github.io/cap-six/`**

### Étape 5 · L'installer
- **iPhone** : ouvre l'adresse dans **Safari** → **Partager** → **Sur l'écran d'accueil** → **Ajouter**. L'appli s'ouvre en plein écran, avec son icône.
- **Mac** : **Safari → Fichier → Ajouter au Dock** (ou Chrome → **Installer la page en tant qu'application**).

### Étape 6 · Synchroniser Mac ↔ iPhone
L'appli enregistre ta progression dans un **Gist secret** de ton compte GitHub (un petit fichier non listé).
1. Sur github.com : ta photo de profil → **Settings** → tout en bas **Developer settings** → **Personal access tokens** → **Tokens (classic)** → **Generate new token (classic)**.
2. **Note** : `Cap Six` · **Expiration** : 90 jours · coche **uniquement** la case **`gist`** → **Generate token**.
3. **Copie le token** (`ghp_…`) : GitHub ne l'affiche qu'une fois.
4. Dans l'appli sur le Mac : **Réglages & aide** (touche `9`) → colle le token → **Activer la synchro Mac ↔ iPhone**.
5. Sur l'iPhone : même chose avec le **même token**. L'appli retrouve toute seule ta progression.

Ensuite, tout se synchronise automatiquement : à chaque case cochée, à l'ouverture de l'appli et toutes les minutes.

> 🔐 Le token donne seulement accès à tes Gists, pas au reste de ton compte. Ne le partage pas. En cas de perte d'un appareil : GitHub → Developer settings → supprime le token, puis crées-en un nouveau.

---

## 4. Modifier l'appli en parlant à Claude

C'est le lien entre l'appli et Claude : tu demandes, Claude modifie le code.

**Le plus simple** : dans l'appli, **Réglages & aide → Demander une modification à Claude**.
1. Écris ce que tu veux (« j'ai raté mardi, replanifie », « ajoute la géométrie S5 », « décale le sport à 7h »).
2. Clique **Copier le message pour Claude** : le message contient ta progression, tes blocs en retard de la semaine, l'état de tes lectures et les liens de l'appli.
3. Colle-le dans Claude (cette conversation ou une nouvelle), avec les PDF éventuels.

Ensuite, Claude :
- met à jour la **version Claude** : elle se recharge sur tous tes appareils ;
- met à jour la **version GitHub** :
  - **si GitHub est relié à Claude**, Claude pousse le nouveau `index.html` dans le dépôt, et GitHub Pages publie en 1 minute ;
  - **sinon**, Claude t'envoie le nouveau `index.html` : dans ton dépôt, **Add file → Upload files**, dépose-le, **Commit changes**.

L'appli installée prend la nouvelle version à la prochaine ouverture.

> Tes cases cochées sont rattachées à un jour et à un créneau : quand Claude modifie le planning, ta progression n'est pas effacée.

Pour que Claude retrouve facilement l'appli dans une nouvelle conversation, donne-lui le lien de l'artefact ou le nom du dépôt (`TON-PSEUDO/cap-six`), ce que fait le bouton automatiquement.

---

## 5. Utiliser l'appli au quotidien

| Vue | Touche | À quoi ça sert |
|---|---|---|
| **Aujourd'hui** | `1` | Ta journée heure par heure. Le bloc en cours est surligné et un trait indique l'heure actuelle. Clique sur un bloc pour voir ses étapes. Le rond le coche. ▶ lance le minuteur de concentration. |
| **Planning** | `2` | La semaine en colonnes. Coche directement ou ouvre un jour. |
| **Calendrier** | `3` | Les 3 mois : plus c'est vert, plus la journée est faite. Les points marquent les échéances. |
| **Matières** | `4` | Les gros objectifs (séries, œuvres, dossiers) à cocher quand c'est vraiment acquis. |
| **Lectures** | `5` | Mets à jour ta page atteinte : l'appli calcule où tu devrais en être aujourd'hui. |
| **Échéances** | `6` | Tout ce qui est noté ou à rendre, avec compte à rebours. |
| **Statistiques** | `7` | Heures faites par matière, régularité sur 21 jours, temps de concentration. |
| **Méthodes** | `8` | Dissertations, essay, oral 15/15, lecture rapide, checklist du test de maths du 4/12. |
| **Réglages & aide** | `9` | Synchro, sauvegarde, installation, demande à Claude. |

**Raccourcis sur Mac** : `←` `→` jour précédent / suivant · `T` aujourd'hui · `F` minuteur sur le bloc en cours · `Espace` cocher le bloc en cours · `⌘K` chercher n'importe quel bloc · `?` aide.

**La routine** : le matin, regarde **Aujourd'hui**. Pour chaque bloc, lance ▶, suis les étapes, coche. Le dimanche, fais le bilan et, si tu as pris du retard, demande à Claude de replanifier avec le bouton de la section 4.

---

## 6. Problèmes fréquents

- **L'appli installée n'affiche pas la dernière version** : ferme-la complètement et rouvre-la (sur iPhone, balaie-la vers le haut dans le sélecteur d'applis).
- **« Token refusé »** : le token a été mal copié, a expiré, ou la case `gist` n'était pas cochée. Crée-en un nouveau.
- **Synchro « Hors ligne »** : pas de connexion. Tout est gardé sur l'appareil et part dès le retour du réseau.
- **La page GitHub affiche une erreur 404** : attends 2 minutes après avoir activé Pages, et vérifie que `index.html` est bien à la racine du dépôt, pas dans un sous-dossier.
- **L'icône ne s'affiche pas** : vérifie que le dossier `icons` a bien été envoyé dans le dépôt.

---

## 7. Structure du code

- `index.html` : toute l'appli (HTML + CSS + JavaScript, sans dépendance). Le planning est dans l'objet `P` (un jour par clé `"AAAA-MM-JJ"`), les lectures dans `READS`, les objectifs dans `ITEMS`, les échéances dans `DEADLINES`.
- `manifest.webmanifest` : nom, icônes et affichage plein écran à l'installation.
- `sw.js` : fonctionnement hors ligne (réseau d'abord, cache en secours).
- `icons/` : icônes de l'appli.

La synchro choisit automatiquement : compte Claude si l'appli tourne dans Claude, sinon Gist GitHub si un token est enregistré, sinon cet appareil seulement.
