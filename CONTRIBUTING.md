# Contribuer au Toolkit Sur les Nuages

Merci de vous intéresser au projet !

Ce repo n'est pas un projet open source classique : il accompagne une **série éditoriale** sur le blog [surlesnuages.fr](https://surlesnuages.fr). Cette particularité change un peu la façon dont j'accepte les contributions, d'où ces quelques notes.

## Avant tout : ce repo est d'un côté éditorial, de l'autre l'hébergement d'une suite d'outils d'administration PowerShell sous forme du module surlesnuages.toolkit

Le contenu de ce repo est lié aux articles publiés. Concrètement :

- Le module `surlesnuages.toolkit/` évolue **au rythme des articles**. Il n'est pas génant d'y ajouter une fonction qui ne correspond pas à un article, mais il faut que celle-ci soit correctement documentées et respectent les bonnes pratiques.
- Le dossier `articles/` contient du **support pédagogique daté**, parfois volontairement imparfait. Ce code n'est **pas** destiné à être amélioré : il illustre des points spécifiques d'un article. N'allez pas ouvrir une issue pour dire "Le premier script d'exemple de l'article sur la documentation des scripts est fouilli et incompréhensible 🥺" : c'est normal ! Par contre, si il y a un problème sur un script qui est censé représenter les bonnes pratiques et le "modèle" de ce qui est à faire, n'hésitez surtout pas !
- Le repo et le blog se renforcent mutuellement. Une modification du repo peut nécessiter une mise à jour d'article, et inversement.

J'insiste : ça veut pas dire qu'il ne faut pas contribuer ! Ca veut dire qu'il faut être vigilant lors de vos contributions.

## Types de contributions bienvenues

### Signalements de bugs

Si un script ne marche pas comme annoncé (même pour les exemples si ils ne font pas ce qui est annoncé), ouvrez une **issue** avec :
- Le script concerné (chemin dans le repo)
- La version de PowerShell utilisée (`$PSVersionTable.PSVersion`)
- L'OS (Windows / Linux / macOS)
- La commande exacte lancée
- Le comportement attendu vs observé
- Si c'est un script avec Logs, les logs (en n'oubliant pas d'anonymiser ce qui est nécessaire !)

### Suggestions d'améliorations

Pour proposer une amélioration sur le module ou un script, **ouvre une issue d'abord**, ne fais pas de PR directe. On discute de l'approche, et si on s'accorde, tu peux soumettre une PR ensuite. Cette étape évite des PR rejetées pour incompatibilité avec la prochaine série éditoriale.

### Suggestion de sujet d'article

Il manque quelque chose dans une de mes séries ? Malgré mes recherches, c'est tout à fait possible ! Ouvez une issue **sur le Repo dédié https://github.com/Arnaud-Ferriere/SurLesNuages** avec le label `idée article`. 
Je ne peux pas faire de promesse de traitement (j'ai un planning éditorial perso et bien entendu une vie à côté), mais les propositions sont prises en compte et appréciées.

### Corrections de typo / clarifications

PR directe acceptée pour :
- Corrections de typos dans les commentaires de code ou la doc
- Reformulation de docstrings unclair
- Correction de liens cassés (uniquement sur la documentation de ce Repo : le site ne devrait pas avoir de problème car une vérification automatique est en place avec Github Actions)

### Code

Pour les vraies modifs de code, on suit ce workflow :
1. Ouvrez une issue pour en discuter
2. Si on est d'accord, forkez le repo
3. Créez une branche `feature/votre-sujet` ou `fix/votre-sujet`
4. Codez en respectant les conventions ci-dessous
5. Soumettez la PR avec une description claire / le N°Issue correspondant

## Conventions de code

Le module est écrit en suivant les bonnes pratiques présentées dans la série. Concrètement :

- **Verbes approuvés** PowerShell uniquement (`Get-Verb` pour la liste)
- **CBH (Command-based Help) complet** sur les fonctions exportées (`Public/`), commentaire-bloc court sur les helpers internes (`Private/`)
- **CmdletBinding** sur toutes les fonctions, avec `SupportsShouldProcess` quand l'opération est destructive
- **Validation des paramètres** via `ValidateScript`, `ValidateRange`, `ValidateSet`...
- **Pas d'aliases** dans le code (pas de `gci`, `?`, `%`...). Cmdlets complets uniquement.
- **Indentation** : 4 espaces, pas de tabs
- **Encoding** : UTF-8 sans BOM
- **Compatibilité** : PowerShell 5.1 minimum, sauf raison documentée

Cette liste grossira probablement à mesure que la série sera publiée.

Pour les détails, voir les articles qui pose les bases de toutes ces conventions.

## Tests

À partir de l'article 4, le repo aura une suite Pester. Les contributions de code devront alors inclure des tests.

## Code de conduite

Soyons respectueux dans les échanges. C'est un repo perso construit sur du temps libre, je réponds quand je peux. 
Une issue qui reste ouverte sans réponse pendant quelques jours n'est pas un manque d'intérêt, je ferais de mon mieux pour faire au plus vite :)

Il n'y aura pas de tolérance pour le harcèlement, les attaques personnelles, ou les commentaires désobligeants. Une issue ou PR qui dérape sera fermée sans discussion.

## Licence des contributions

Toute contribution acceptée tombe sous la même license [MIT](LICENSE) que le reste du repo.

Attention :
- le Repo avec le Toolkit et le code (https://github.com/Arnaud-Ferriere/toolkit-surlesnuages/) est sous licence MIT
- le Repo du site et des articles lui (https://github.com/Arnaud-Ferriere/SurLesNuages) est sous licence CC-BY-4.0

## Une question ?
Si vous hésitez avant de contribuer, ouvrez une issue avec le label `question`. 
N'hésitez pas non plus à me contacter directement (mail, LinkedIn, commentaire sur un article etc)
Merci ! 
