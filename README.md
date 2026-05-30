# 🌙 Moon Craft — Modpack NeoForge 1.21.1

Dépôt de distribution du modpack **Moon Craft** (serveur MMORPG style Paladium).
Le launcher lit [`manifest.json`](manifest.json) et télécharge automatiquement les fichiers
depuis les **Releases GitHub**.

## Contenu

- **11 mods** Moon Craft (NeoForge 1.21.1) : MoonCore, MoonCombat, MoonWorld, MoonQuests,
  MoonEconomy, MoonDungeons, MoonGuildes, MoonCosmetics, MoonGuard, MoonJobs, MoonEssentials
- **GeckoLib** (dépendance d'animation)
- **Resource pack officiel**

## Manifest

`manifest.json` (schéma NeoForge) :

```json
{
  "version": "2.0.0",
  "minecraft": "1.21.1",
  "loader": "neoforge",
  "neoforge": "21.1.77",
  "java": 21,
  "files": [ { "path": "...", "url": "...", "sha256": "...", "size": 0 } ]
}
```

Chaque fichier est vérifié par **SHA-256** au téléchargement.

## Publication d'une mise à jour

1. Compiler les mods, mettre les jars à jour.
2. Régénérer `manifest.json` (sha256 + size).
3. `gh release create vX.Y.Z mods/*.jar resourcepacks/*.zip manifest.json`
4. Commit du nouveau `manifest.json`.

Le launcher détecte la nouvelle version au prochain lancement et met à jour automatiquement.
