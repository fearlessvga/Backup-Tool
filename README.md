# Backup Tool @fearlessvga

Outil en ligne de commande pour sauvegarder, restaurer et gérer des serveurs Discord. Interface interactive, sauvegardes illimitées et support bilingue (français / anglais).

## Fonctionnalités

- **Créer une backup** — Sauvegarde complète d'un serveur (rôles, salons, permissions, bannissements, emojis, icône, bannière, etc.)
- **Backup avec messages** — Inclut l'historique des messages via webhooks
- **Backup + import** — Crée une backup puis la restaure directement sur un autre serveur
- **Backup des emojis** — Sauvegarde et restauration des emojis personnalisés
- **Créer un template** — Génère un lien de template Discord (`discord.new`)
- **Charger une backup** — Restaure une sauvegarde existante sur un serveur
- **Lister les backups** — Affiche toutes les sauvegardes disponibles
- **Supprimer des salons** — Supprime les salons d'une catégorie donnée

## Prérequis

- [Node.js](https://nodejs.org/) v16 ou supérieur
- Un compte Discord avec les permissions nécessaires sur le serveur cible
- Windows (scripts `.bat` fournis) ou tout OS compatible Node.js

## Installation

### Windows (recommandé)

1. Clonez le dépôt :
   ```bash
   git clone https://github.com/fearlessvga/BackupTool.git
   cd BackupTool
   ```

2. Lancez le script d'installation :
   ```bat
   install.bat
   ```

### Installation manuelle

```bash
npm install
```

## Configuration

Modifiez le fichier `config.json` à la racine du projet :

```json
{
    "token": "votre_token_ici",
    "language": "en",
    "color": "blue"
}
```

| Champ      | Description                                      | Valeurs possibles        |
|------------|--------------------------------------------------|--------------------------|
| `token`    | Token de votre compte ou bot Discord             | —                        |
| `language` | Langue de l'interface                            | `"en"` ou `"fr"`         |
| `color`    | Couleur du thème dans le terminal                | `"blue"`, `"cyan"`, etc. |

> **Important :** Ne partagez jamais votre token et ne le commitez pas sur GitHub. Ajoutez `config.json` à votre `.gitignore`.

## Utilisation

### Windows

Double-cliquez sur `start.bat` ou exécutez :

```bat
start.bat
```

### Ligne de commande

```bash
npm start
```

Un menu interactif s'affiche dans le terminal. Suivez les instructions à l'écran (saisie de l'ID du serveur, de la backup, etc.).

### Permissions requises

| Action                        | Permission Discord              |
|-------------------------------|---------------------------------|
| Backup / restauration complète| `ADMINISTRATOR`                 |
| Backup des emojis             | `MANAGE_EMOJIS_AND_STICKERS`    |
| Suppression de salons         | `MANAGE_CHANNELS`               |
| Création de template          | `MANAGE_GUILD`                  |

## Structure du projet

```
BackupTool/
├── backups/          # Sauvegardes de serveurs (générées automatiquement)
├── emotes/           # Sauvegardes d'emojis
├── config.json       # Configuration (token, langue, couleur)
├── index.jsc         # Code source compilé (bytenode)
├── install.bat       # Script d'installation Windows
├── start.bat         # Script de lancement Windows
├── package.json
└── README.md
```

## Dépendances principales

| Package                  | Rôle                                      |
|--------------------------|-------------------------------------------|
| [discord-backup](https://www.npmjs.com/package/discord-backup) | Création et restauration des backups |
| [discord.js-selfbot-v13](https://www.npmjs.com/package/discord.js-selfbot-v13) | Connexion au client Discord |
| [bytenode](https://www.npmjs.com/package/bytenode) | Exécution du code compilé |
| [gradient-string](https://www.npmjs.com/package/gradient-string) | Affichage coloré dans le terminal |
| [readline-sync](https://www.npmjs.com/package/readline-sync) | Menus interactifs en CLI |

## Avertissement

Cet outil utilise un **selfbot** (connexion via le token utilisateur). L'utilisation de selfbots est **interdite par les [Conditions d'utilisation de Discord](https://discord.com/terms)** et peut entraîner la suspension de votre compte.

Utilisez cet outil à vos propres risques, uniquement sur des serveurs dont vous êtes propriétaire ou administrateur, et à des fins de sauvegarde légitime.

## Licence

[MIT](LICENSE) — © Sans
