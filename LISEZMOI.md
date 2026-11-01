# Logithèque Cyberia

Vitrine publique des applis du fablab. La page (`index.html`) lit la liste des applis dans `apps.json` : pour ajouter ou modifier une appli, on ne touche qu'à `apps.json`.

## Mise en ligne (une seule fois)

1. Sur github.com : **New repository** → nom `logitheque` → **Public** → *Create repository*.
2. *uploading an existing file* → glisser `index.html`, `apps.json` et ce fichier → *Commit changes*.
3. *Settings* → *Pages* → *Source* : **Deploy from a branch** → branche `main`, dossier `/ (root)` → *Save*.
4. Une ou deux minutes plus tard, la vitrine est en ligne sur `https://xtofm.github.io/logitheque/`.

C'est cette adresse qu'on donne au public, ou qu'on met derrière un bouton ou un QR code sur le site de la commune.

## Ajouter ou modifier une appli

1. Ouvrir `apps.json` sur github.com → icône crayon (*Edit*).
2. Copier un bloc `{ ... }` existant, le coller à la suite, et le remplir.
3. *Commit changes*. La page se met à jour en une minute environ.

Les blocs sont séparés par une virgule, sauf après le dernier. Si la page affiche « erreur de syntaxe », c'est presque toujours une virgule ou un guillemet.

| Champ | Exemple | Remarque |
|---|---|---|
| `nom` | `"Tournoi de pétanque"` | obligatoire |
| `sigle` | `"TP"` | lettres affichées dans la vignette quand il n'y a pas de capture (4 caractères max) ; vide = calculées depuis le nom |
| `pour` | `"les clubs et associations"` | s'affiche « Pour … » |
| `description` | `"Organise un concours…"` | deux ou trois phrases simples |
| `version` | `"1.2"` | |
| `systeme` | `"Windows 10 et 11"` | |
| `taille` | `"38 Mo"` | |
| `lien` | `"https://github.com/xtofm/petanque/releases/latest/download/Petanque-Setup.exe"` | lien **direct** vers le fichier ; vide = « Bientôt disponible » |
| `image` | `"images/petanque.png"` | capture facultative, déposée dans un dossier `images/` du dépôt |
| `masquee` | `true` / `false` | `true` = fiche cachée au public (brouillon) |
| `type` | `"web"` | facultatif : pour une page web, le bouton devient « Ouvrir dans le navigateur » au lieu de « Télécharger » |

## Lien de téléchargement direct depuis une release GitHub

Pour une release de l'appli, ce lien pointe toujours vers la dernière version, à condition de garder le même nom de fichier d'une version à l'autre :

```
https://github.com/xtofm/NOM-DU-DEPOT/releases/latest/download/NOM-DU-FICHIER.exe
```

## Tester

Ouvrir `index.html` en double-cliquant dessus ne marche pas (le navigateur bloque la lecture de `apps.json`) : il faut passer par l'adresse GitHub Pages.
