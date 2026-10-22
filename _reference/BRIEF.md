# Référence visuelle pour la refonte du portfolio

- Vidéo de référence : `_reference/intro-animation.mp4` (7 s). Extraire des images avec `ffmpeg -i _reference/intro-animation.mp4 -vf fps=4 /tmp/f%03d.png` si besoin.
- Captures déjà extraites (2 images/s, dans l'ordre) : `_reference/frames/t01.png` … `t14.png`, et la planche complète `_reference/frames/planche.png`. **Regarde-les avant de coder.**
- La photo de Yahya est déjà dans `index.html` (image base64 de la balise `<img>` dans `.rail .portrait`) : réutilise-la pour le portrait en particules. Son fond est du bois : isole la personne (masque tête + buste) pour ne pas dessiner le fond.
- Le dossier `_reference/` commence par un underscore : GitHub Pages (Jekyll) ne le publie pas. Ne le supprime pas.

## Brief

Refais la page d'accueil (hero + intro) du portfolio dans ce dépôt (`yahyabenyaflah/yahyabenyaflah.github.io`, site GitHub Pages en HTML) pour reproduire l'animation d'intro décrite ci-dessous. Garde le contenu existant (sections, projets, liens, textes) mais adapte le style global au nouveau thème sombre. Reste en HTML/CSS/JS statique compatible GitHub Pages (pas de build obligatoire ; libs via CDN autorisées, ex. GSAP, ou canvas natif).

Animation de référence (~7 s, fond noir avec un léger halo radial gris au centre) :
1. 0–1 s : un petit point blanc lumineux seul au centre de l'écran.
2. 1–2 s : le point « frappe » une petite barre blanche inclinée qui balaie de gauche à droite et révèle les lettres du nom une à une, jusqu'à « YAHYA ». Typo : sans-serif très grasse, majuscules (ex. Inter 900 / Archivo Black), lettres avec un dégradé vertical métallique blanc → gris.
3. 2–3 s : effet « scramble » : les lettres se transforment progressivement en « PORTFOLIO » (étape intermédiaire visible : mélange des deux mots).
4. 3–4 s : « PORTFOLIO » descend et grossit vers le bas de l'écran (position hero, quasi toute la largeur). Dessous, à gauche : « **Développeur** *Full-Stack* » (1er mot gras blanc, 2e italique fin) ; à droite un petit bouton rond avec une flèche ↙ et un bouton pilule « Contact ».
5. 4–5 s : la navbar apparaît en fondu : à gauche « MOHAMED YAHYA BEN YAFLAH » (petites capitales grasses, letter-spacing), à droite HOME · ABOUT · SERVICE · PROJECT · CONTACT (petits, majuscules, lien actif souligné), adaptés aux sections réelles du site.
6. 5–7 s : un nuage de particules (petits carrés gris-bleu) se rassemble au centre et compose le portrait de Yahya en style halftone/mosaïque pixellisée (canvas : échantillonner la photo, carrés dont la luminosité suit l'image, teinte bleu-gris), placé derrière le mot PORTFOLIO qui chevauche le buste. Ensuite les particules flottent légèrement et réagissent au survol de la souris.

L'animation se joue une fois au chargement ; gérer `prefers-reduced-motion` (état final direct) et un rendu mobile propre (PORTFOLIO tient en largeur, nav en burger).

Photo : utilise la photo de Yahya déjà présente dans le dépôt si elle existe ; sinon placeholder `assets/portrait.jpg` et signale-le.

Fini quand : la séquence se joue, le reste du site fonctionne, aucune erreur console, testé desktop + mobile. Commit sur une branche, push, ouvre une PR (sans merger) avec résumé et captures.
