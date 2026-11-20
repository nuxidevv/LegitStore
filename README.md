## Ajouter une application

1. Crée un dossier dans `apps/`, par exemple `apps/mon-app/`.
2. Ajoute un fichier `app.ipa` ou `install.txt` dans ce dossier.
3. Ajoute une entrée dans `apps.json` :

```json
{
  "apps": [
    {
      "id": "mon-app",
      "name": "Mon application",
      "subtitle": "Productivité",
      "description": "Description de l’application.",
      "category": "Utilitaires",
      "version": "1.0",
      "size": "25 Mo",
      "icon": "./apps/mon-app/icon.png",
      "installFile": "install.txt",
      "updated": "2026-11-20",
      "tags": ["outil", "productivité"]
    }
  ]
}
```

- Pour un lien externe : `installFile` doit pointer vers `install.txt`. Le fichier texte doit contenir une URL `https://...`.
- Pour un IPA : utilise `"installFile": "app.ipa"`. Le site le téléchargera.
- Pour une distribution iOS OTA prise en charge, configure un manifeste HTTPS valide avec `"manifestUrl": "https://exemple.com/manifest.plist"`. Le manifeste doit référencer une application correctement signée et hébergée en HTTPS.
- `icon` peut être un chemin vers une image ou une URL HTTPS.

Le champ `id` doit être unique et correspondre exactement au nom du dossier sous `apps/`.

## Important — installation iOS

Un site web ne peut pas installer arbitrairement un IPA. Un IPA doit être signé et distribué selon les mécanismes pris en charge par Apple. Le téléchargement du fichier ne signifie pas que l’application sera installable.
