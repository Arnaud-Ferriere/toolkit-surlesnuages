Ce repo accompagne la série **Bonnes pratiques PowerShell** sur mon site [Sur les Nuages](https://surlesnuages.fr). 

Les articles construisent au fur et à mesure un vrai toolkit : modules, scripts d'exemple, tests, pipeline de publication. Ce qui est expliqué dans les articles est appliqué ici, et inversement.

Concrètement, vous trouverez :

- Un module **SLN.Toolkit** : fonctions réutilisables pour les tâches courantes M365 / Entra ID / Active Directory etc
- Des **scripts utilitaires** standalone (génération de sandbox, etc.)
- Le **support pédagogique** des articles : versions intermédiaires, exemples volontairement imparfaits utilisés pour illustrer les bonnes pratiques
- À terme : tests Pester / PSScriptAnalyzer, doc générée par PlatyPS, pipeline GitHub Actions 

## Pour qui ?

- Admins M365 / sysadmin Windows qui scriptent en PowerShell régulièrement
- Devs/SREs qui touchent à Entra ID, Microsoft Graph, ou l'écosystème Microsoft cloud
- Toute personne qui veut voir un module PowerShell évoluer **en public**, avec son histoire 

## Structure du repo

```
toolkit-surlesnuages/
├── modules/
│   └── SLN.Toolkit/             # Module principal (fonctions exportées)
│       ├── SLN.Toolkit.psd1
│       ├── SLN.Toolkit.psm1
│       ├── Public/              # Fonctions exportées
│       └── Private/             # Helpers internes
├── tools/                       # Utilitaires hors module
├── articles/                    # Supports pédagogiques par article
│   └── 01-documenter-scripts/
│       ├── README.md            # Contexte de l'article
│       ├── New-TestSandbox.ps1  # Génère une arborescence de test
│       ├── show-tree-v1.ps1     # Volontairement imparfait
│       ├── show-tree-v2.ps1     # Version corrigée
│       └── ...
├── tests/                       # Suite Pester (à partir de l'article 4)
├── docs/                        # Doc générée (à partir de l'article 3)
├── .github/
│   └── workflows/               # Pipeline CI/CD (à partir de l'article 6)
└── README.md
```

> [!NOTE] Le contenu de `articles/` peut contenir du code **volontairement mal écrit**, utilisé comme exemple pédagogique dans les articles. Ils sont indiqués dans les README.md de chaque dossiers. Ne les copiez pas tel quel pour de la prod, préférez plutôt les versions du module `SLN.Toolkit/` pour le code de référence.

## Articles de la série

État de la série au fil de la publication. Chaque article ajoute une brique au toolkit.

|#|Article|Apport au toolkit|Statut|
|---|---|---|---|
|1|Documenter ses scripts PowerShell|Documentation des scripts PowerShell, premiers exemples dans `articles/01-documenter-scripts/`|⏳ À venir|
|2|Microsoft Graph en PowerShell|Helpers d'authentification, wrapper de pagination, gestion du throttling|⏳ À venir|
|3|Créer un module PowerShell propre|Packaging dans `SLN.Toolkit/`, manifest, exports, doc PlatyPS|⏳ À venir|
|4|Tester avec Pester v5|Suite de tests dans `tests/`|⏳ À venir|
|5|Sécuriser ses scripts|Intégration `SecretManagement`, gestion des credentials|⏳ À venir|
|6|CI/CD avec GitHub Actions|Pipeline complète : build, tests, publication PSGallery|⏳ À venir|

## Contribuer

Le repo accepte les **issues** pour signaler un bug, suggérer une amélioration, ou proposer un sujet pour un futur article. Les **PR** sont bienvenues, mais gardez en tête que le contenu est lié à une série éditoriale : un changement majeur dans le module pourrait nécessiter de réécrire un article.
N'hésitez pas à ouvrir une issue d'abord pour q'on discute de l'approche : le contenu est et sera toujours améliorable !

## License

Ce repo est publié sous license [MIT](LICENSE).
Le texte complet de la license est dans le fichier [LICENSE](LICENSE).

## Contact

- Blog : [surlesnuages.fr](https://surlesnuages.fr/)
- Articles connexes : tag [`PowerShell`](https://surlesnuages.fr/tags/PowerShell) sur le blog
- Issues : utilisez l'onglet [Issues](https://github.com/%3Cton-handle%3E/toolkit-surlesnuages/issues) du repo
