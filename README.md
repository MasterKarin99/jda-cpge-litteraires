# Prépa littéraire Jeanne d'Albret — Hypokhâgne & Khâgne

Site de la classe préparatoire littéraire (hypokhâgne et khâgne) du lycée Jeanne d'Albret, à Saint-Germain-en-Laye.

## Pages

- `index.html` : accueil (la prépa, le cursus, l'admission, les débouchés, l'internat, les dernières actualités, les témoignages, le contact)
- `actualites.html` : les actualités, avec des filtres par thème et par classe et la lecture de chaque article (lien direct : `actualites.html#<id-article>`)
- `temoignages.html` : les témoignages d'anciennes et d'anciens étudiants, en vidéo et en récit

## Structure

```
assets/img/     photos des articles, logo, internat
assets/video/   vidéos des articles et des témoignages
data/news.json  les 72 articles (texte, images, catégories)
```

Site statique, sans dépendance ni étape de build. Il est publié avec GitHub Pages depuis la branche `main`.

## Ajouter une actualité

Ajouter un objet en tête du tableau `data/news.json`, avec les champs suivants :

- `id`, `date` (AAAA-MM-JJ), `dateLabel`, `year` (année scolaire, par ex. `2026-2027`)
- `title`, `cat`, `level` (`Hypokhâgne`, `Khâgne` ou `Hypokhâgne & khâgne`), `excerpt`, `credit`
- `hero`, sous la forme `{ "u": "assets/img/…", "w": …, "h": … }`
- `blocks` : le contenu de l'article. Types de blocs :
  - `h` : intertitre
  - `p` : paragraphe
  - `li` : élément de liste
  - `quote` : citation
  - `sig` : signature
  - `gal` : galerie d'images
  - `video` : vidéo
  - `table` : tableau

Dans un bloc de texte, chaque morceau (`runs`) a un champ `k` qui vaut `n` (normal), `b` (gras), `i` (italique), `bi` (gras italique) ou `a` (lien, avec `h` pour l'adresse).

## Tester en local

```
python3 -m http.server 8000
```

puis ouvrir http://localhost:8000.
