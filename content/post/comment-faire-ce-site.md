---
title: "Comment faire ce site ?"
date: 2021-01-03T04:11:59+01:00
hero: "/images/comment-faire-ce-site.jpg"
draft: false
---

J'écris ce tutoriel au fur et à mesure que j'avance dans ma progression. Cela me permet de garder des notes si un jour j'ai à le refaire mais cela m'aide surtout à mieux assimiler les nouveaux concepts. 
C'est certainement dû au fait que j'applique une première fois les concepts rapidement dans mon code et que je revienne dessus quelques minutes après en approfondissant pour rédiger l'article.pour rédiger l'article).

## Installation

Commencer par installer Go et Hugo.
Je suis sur Ubuntu 20.10

```sh
sudo apt update
install golang-go hugo
```

On génère un nouveau site Hugo :

```sh
hugo new site pierre.aboucaya.name
```

On initialise un dépôt Git :

```sh
cd pierre.aboucaya.name
git add .
git commit -m "Installation fraîche"
```

On installe le thème :
N'y connaissant rien, j'ai vu qu'il était conseillé de le faire avec des modules Go donc voici :

```sh
hugo mod init pierre.aboucaya.name/m
```

J'ai modifié la configuration par défaut dans config.toml pour y inclure le thème ainsi que quelques variables de configuration. Voici mon config.toml après configuration :

```toml
baseURL = "https://pierre.aboucaya.name/"
languageCode = "fr"
title = "Pierre Aboucaya"

# Theme
theme = "github.com/forestryio/hugo-theme-novela"

paginate = 6

[social]
twitter= "https://twitter.com/pierreaboucaya"
github= "https://github.com/asper"
linkedin= "https://www.linkedin.com/pierreaboucaya"
instagram = "#"
dribbble = "#"
youtube = "#"

[taxonomies]
author = "authors"
```

On crée un premier article pour voir si tout fonctionne (c'est d'ailleurs l'article que vous êtes en train de lire en ce moment même !).

```sh
hugo new post/comment-faire-ce-site.md
```

Puis on lance le serveur de développement pour vérifier que tout s'est bien passé (avec l'option -D pour forcer l'affichage des brouillons) :

```sh
hugo server -D
```

Un des aspects sympas du serveur de développement Hugo est qu'il surveille les modifications que vous effectuez aux posts. Dès qu'un post est modifié, il recompile le HTML et envoie un signal au navigateur pour lui indiquer de recharger la page. Le tout en 10 ms chez moi !

Au passage j'ai vu qu'il manquait une illustration à mon post. J'ai donc effectué un détour de quelques heures pour définir le style des images du site. Comme ce n'est pas l'objet de ce tutoriel, nous allons passer cette étape mais si cela vous intéresse sachez que c'est l'objet de [mon prochain post](/prochain-post/).

La on va se contenter d'insérer l'image produite dans l'article. L'image doit faire 1588*850px et être placée dans  pour cela on ajoute un header à l'article :

```sh
hero: "/images/comment-faire-ce-site.jpg"
```


https://developers.cloudflare.com/pages/how-to/deploy-a-hugo-site
github.com/forestryio/hugo-theme-novela

