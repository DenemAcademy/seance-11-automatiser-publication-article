# Séance 11 - Automatiser sa publication d'article

## Résumé pédagogique

Je construis un système de blog automatique à partir du site RestIA déjà créé. L'objectif n'est pas seulement de générer du texte : je veux préparer un workflow où Codex comprend la structure du blog, analyse les fichiers SEO, crée un plan éditorial, génère les articles, ajoute les images, planifie les publications WordPress, puis corrige les articles déjà programmés si le ton ne convient pas.

La séance montre aussi la réalité du travail : Codex peut produire une structure techniquement bonne mais avec un ton trop "template". Le bon réflexe n'est pas de tout recommencer. Je reprends les articles planifiés, je diagnostique le problème, puis je demande une correction globale.

## Timeline des moments importants

| Timecode | Moment | Ce que je fais | Ce que tu dois retenir |
|---|---|---|---|
| 00:00:00 | Introduction | Je présente la création d'articles automatiques. | La séance avance étape par étape, pas en mode magie. |
| 00:00:26 | Dossier de travail | Je pars de la partie blog et je déplace les dossiers utiles. | Codex doit avoir le bon contexte local avant de travailler. |
| 00:01:12 | Terminal | J'ouvre un terminal dans le dossier et je lance Codex en mode YOLO. | Le mode rapide exige un dossier propre et une mission précise. |
| 00:01:31 | Connexion WordPress | Je demande à Codex d'ouvrir le site WordPress via MCP/Chrome. | Je travaille dans l'interface réelle, pas seulement dans des fichiers. |
| 00:02:48 | Analyse du blog | Je demande à Codex d'analyser la structure existante. | Le blog automatique doit respecter le design et les champs déjà en place. |
| 00:03:27 | Documents de contexte | Je donne les fichiers de structure et d'audit SEO. | Plus Codex a de contexte, moins il invente. |
| 00:04:33 | Exigence qualité | Je précise que les articles doivent être professionnels et utiles pour SEO/GEO. | Automatiser ne veut pas dire publier du contenu faible. |
| 00:06:09 | Maillage interne | J'explique que les articles doivent se relier entre eux et vers le site. | Le maillage est pensé dès le plan éditorial. |
| 00:08:22 | Premier article test | Je demande un sujet issu de l'audit SEO et un article complet. | Avant 200 articles, je valide le fonctionnement sur un article. |
| 00:10:52 | Images | Je demande des images avec l'API et des champs alt/titre/légende. | Chaque article doit avoir ses images, pas une image réutilisée partout. |
| 00:16:06 | Publication ou brouillon | Je réfléchis à la publication programmée plutôt qu'aux brouillons manuels. | Tu peux choisir brouillon ou publication, mais la cadence doit être claire. |
| 00:20:29 | Programmation WordPress | Je veux vérifier si Codex sait programmer un article via WordPress. | La planification est une preuve forte d'automatisation. |
| 00:25:10 | Correction image | Je repère que la demande image ne donne pas exactement ce que je veux. | Quand une étape n'est pas parfaite, je note le problème sans interrompre trop tôt. |
| 00:27:11 | Audit SEO parallèle | J'ouvre l'audit SEO pour ne pas perdre de temps. | Travailler sur plusieurs terminaux peut accélérer les longues générations. |
| 00:34:38 | Clé API one-shot | Je donne une clé API en dur pour générer, puis je prévois de la retirer. | Une clé temporaire doit être supprimée après usage. |
| 00:39:03 | Plan éditorial enrichi | Je demande le maillage et la planification à partir du 9 juin à 10h45, tous les 3 jours. | Le plan éditorial devient un fichier de production. |
| 00:48:20 | JSON et mapping | Codex prépare un JSON puis mappe les données pour rédiger les articles. | Le JSON sert de structure entre planning, rédaction et publication. |
| 01:04:46 | Articles générés | Les articles sont rédigés avec structure, maillage, liens externes et blocs images. | Une génération longue se vérifie par lots, pas seulement à la fin. |
| 02:04:12 | Vérification WordPress | Je vérifie que les articles, images, URL et descriptions sont présents. | La preuve finale se fait dans WordPress. |
| 02:07:27 | Ton éditorial | Je repère des phrases que je n'aime pas. | Un contenu automatique peut être techniquement bon mais éditorialement trop faible. |
| 02:10:29 | Correction globale | Je demande une version plus clinique/naturelle sur les articles déjà programmés. | L'intérêt du système : corriger 20, 100 ou 300 articles avec un prompt. |
| 02:18:01 | Diagnostic | Je reconnais un mauvais cadrage de prompt et je demande ce qui ne va pas. | Les erreurs de prompt font partie de la méthode. |
| 02:28:36 | Nouvelle version | Les articles corrigés correspondent mieux à ce que je veux. | La structure était bonne ; le contenu devait être affiné. |
| 02:30:18 | Liens à retirer | Je repère des liens de redirection qui ne fonctionnent pas et je demande de les retirer. | La dernière vérification porte aussi sur les liens et blocs inutiles. |
| 02:34:25 | Valeur business | Je relie cette méthode à une prestation facturable avec maintenance. | Le système a une vraie valeur client quand il est fiable et corrigeable. |

## Prompts et demandes clés reconstruits

### Ouvrir WordPress dans Chrome / MCP

```text
ouvre un navigateur chrome sur cette page stp
https://restia.fun/wp-admin/edit.php?post_type=page
```

Objectif : connecter Codex à la session WordPress réelle pour travailler dans l'admin.

### Analyser la structure du blog

```text
Analyse la structure actuelle de mon blog RestIA.
Regarde les pages, les articles, les champs WordPress, les éléments SEO, les images et les fichiers présents dans le dossier.
Je veux que tu comprennes la structure avant de créer ou publier quoi que ce soit.
```

Objectif : éviter que Codex produise un article isolé qui ne respecte pas le site.

### Créer un premier article à partir de l'audit SEO

```text
Analyse le dossier d'audit SEO et récupère un sujet pertinent.
Ne choisis pas un sujet au hasard.
Prépare un article complet au format réutilisable dans la structure RestIA :
- contenu HTML ;
- champs SEO ;
- liens internes ;
- sources ;
- images ;
- titre, extrait, slug, catégorie.
```

Objectif : valider un article test avant de passer à la génération en lot.

### Enrichir le plan éditorial avec maillage et planning

```text
okay maintenant tu vas enrichir le plan éditorial pour le SEO.
Je veux faire du maillage interne entre les 20 articles.
Rajoute une colonne "Maillage interne recommandé".
Exemple : article 1 maillage avec page d'accueil / page service / contact.
Ensuite article 2 maillage avec article 1, etc.
Il faut une vraie stratégie pour se lier entre les 20 articles.
Rajoute également une colonne "Planification publication".
Ça commence à partir du 9 juin à 10h45.
Je veux publier un article tous les 3 jours.
```

Objectif : transformer le planning en fichier exploitable par WordPress.

### Générer les images

```text
Pour chaque article, prépare 4 prompts image cohérents avec le sujet.
Les images doivent être différentes d'un article à l'autre.
Prépare aussi le texte alternatif, le titre, la légende et la description.
N'utilise pas une image générique répétée.
```

Objectif : éviter les images dupliquées et préparer les champs utiles au SEO/GEO.

### Publier ou programmer dans WordPress

```text
Publie les articles dans WordPress en respectant le planning.
Chaque article doit avoir :
- le bon titre ;
- le slug ;
- la catégorie ;
- l'extrait ;
- le contenu ;
- les images ;
- les champs SEO ;
- les liens internes ;
- le statut programmé à la bonne date.
```

Objectif : ne pas finir avec 20 brouillons à publier à la main.

### Diagnostiquer le problème éditorial

```text
Comprends le vrai problème des articles.
Ne corrige pas seulement une phrase.
Analyse ce qui sonne trop template, trop commercial ou trop artificiel.
Fais-moi un récap clair avant de modifier.
```

Objectif : corriger le ton global, pas seulement supprimer un bloc.

### Corriger les 20 articles

```text
Corrige les 20 articles déjà planifiés.
Garde la structure, les images, les dates, les slugs, les catégories et les champs SEO.
Supprime les passages qui sonnent comme des consignes internes.
Réécris le contenu dans un ton plus naturel, concret et utile pour un restaurateur.
Ne mentionne pas RestIA à la troisième personne dans le contenu.
```

Objectif : conserver la base technique tout en améliorant la qualité éditoriale.

### Retirer les liens ou blocs problématiques

```text
Les liens de redirection ne fonctionnent pas.
Retire les liens ou blocs concernés de tous les articles.
Ne touche pas au reste de la structure.
Vérifie ensuite qu'il ne reste plus de lien cassé visible dans les articles.
```

Objectif : nettoyer un problème transversal sans refaire toute la génération.

## Points de vigilance

- Ne pas publier en masse sans vérifier un premier article.
- Ne pas confondre volume et qualité.
- Ne pas laisser une clé API en clair après la génération.
- Ne pas réutiliser la même image sur tous les articles.
- Ne pas garder des blocs internes du type "points de contrôle".
- Ne pas accepter un ton trop commercial si l'article doit parler à un restaurateur.
- Ne pas oublier le maillage interne avant la publication.
- Ne pas pousser la vidéo lourde dans le repo GitHub Pages.

## Preuves de réussite

- Les articles sont visibles dans WordPress.
- Les dates de publication sont programmées à partir du 9 juin 2026 à 10h45, puis tous les 3 jours.
- Chaque article a ses images et ses champs image.
- Les articles ont une structure cohérente : titre, intro, sommaire, sections, FAQ/conclusion selon besoin.
- Le maillage interne est présent.
- Les contenus ne contiennent plus de notes internes visibles.
- Les liens cassés ou inutiles sont retirés.
- Le système permet de corriger un lot complet avec une seule demande bien cadrée.
