# SalesTouch

[English](../README.md) · [Français](fr.md) · [Deutsch](de.md) · [Español](es.md) · [Português](pt.md) · [Italiano](it.md)

**La prospection LinkedIn pour les agents IA.** SalesTouch est un MCP LinkedIn qui connecte Claude à la recherche de prospects, aux conversations, aux messages, aux publications, aux relances et aux files d’attente. SalesTouch n’est ni affilié à LinkedIn ni approuvé par LinkedIn.

## Prérequis

Un espace SalesTouch avec une offre active et un compte LinkedIn connecté. Les fonctions Sales Navigator nécessitent les accès correspondants. Les résultats dépendent des autorisations, des données disponibles et des limites de la plateforme.

## Installer dans Claude Code

Exécutez dans Claude Code :

```text
/plugin marketplace add antoineDsh/SalesTouch
/plugin install salestouch@salestouch
```

Redémarrez Claude Code, lancez `/mcp`, choisissez SalesTouch et autorisez la connexion dans le navigateur. Ne mettez jamais votre mot de passe LinkedIn, un cookie ou une clé API dans la conversation ou la configuration du plugin.

## Installer dans Claude Desktop ou Cowork

Ouvrez **Customize → Plugins**. Dans **Personal plugins**, choisissez **+ → Add marketplace**, puis l’option de dépôt et saisissez `antoineDsh/SalesTouch`. Installez et activez `salestouch`, puis autorisez son connecteur SalesTouch. Les commandes disponibles dépendent de votre offre Claude et des réglages de votre organisation.

## Cursor

Clonez ce dépôt public dans `~/.cursor/plugins/local/salestouch`, puis rechargez Cursor. Ouvrez **Settings → Tools & MCPs**, repérez `salestouch`, cliquez sur **Connect** et autorisez SalesTouch dans le navigateur. Votre organisation peut limiter les plugins locaux. Le référencement dans la marketplace reste soumis à la validation de Cursor.

Vous pouvez aussi ajouter la [configuration MCP](../../../README.md#cursor) dans `.cursor/mcp.json` pour le projet ou `~/.cursor/mcp.json` pour votre profil. Terminez rapidement l’autorisation : Cursor peut arrêter l’attente après 30 secondes. Dans ce cas, cliquez à nouveau sur **Connect**. Commencez par le prompt de vérification des comptes ci-dessous. Gardez les approbations d’outils activées et vérifiez destinataires et contenus avant toute action externe.

Le plugin MIT est gratuit à installer. Le service SalesTouch hébergé nécessite un abonnement distinct. Ne placez aucun identifiant LinkedIn dans la configuration MCP.

## Trois prompts pour commencer

1. « Liste mes comptes LinkedIn connectés avec SalesTouch. »
2. « Recherche ce profil LinkedIn et ses publications récentes, puis rédige un message d’introduction pertinent sans l’envoyer : [URL du profil]. »
3. « Lis cette conversation LinkedIn, résume les besoins du prospect et prépare une réponse sans l’envoyer : [identifiant de conversation ou URL du profil]. »

Remplacez les valeurs entre crochets par vos cibles. Vous pouvez aussi extraire des résultats de recherche ou les personnes ayant interagi avec une publication, parcourir les résultats enregistrés et télécharger des exports. Vérifiez le destinataire, le contenu et l’horaire avant d’approuver une action. Une action en attente n’est pas livrée. Consultez la file avant de relancer une écriture.

## Connexion et aide

L’endpoint MCP distant est `https://www.salestouch.io/api/mcp`, avec Streamable HTTP et OAuth. En cas d’échec, reconnectez le connecteur, vérifiez l’espace et la connexion LinkedIn, puis relancez le prompt des comptes. Fournissez au support un code d’erreur et des étapes de reproduction sans identifiants, jetons ni messages privés.

[Configuration](../SETUP.md) · [Support](https://www.salestouch.io/support) · [Sécurité](../SECURITY.md) · [Documentation](https://www.salestouch.io/docs) · [Confidentialité](https://www.salestouch.io/privacy) · [Conditions](https://www.salestouch.io/terms) · [support@salestouch.io](mailto:support@salestouch.io)

Les fichiers du plugin sont sous [licence MIT](../LICENSE). Le backend hébergé est propriétaire.

## Version 0.9.3

Installez SalesTouch localement dans Cursor, connectez-le par OAuth et commencez par vérifier les comptes. Le paquet Cursor inclut désormais son logo et des instructions plus claires.

## Version 0.9.2

Connexion Claude Code corrigée : seules les autorisations nécessaires au MCP sont demandées.

## Version 0.9.1

Installation actualisée en six langues ; aide et configuration incluses dans le paquet ; analytics MCP techniques sans objectifs de conversation ni contenu des appels. [Historique](../CHANGELOG.md).
