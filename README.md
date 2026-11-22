# Polizei-Portal – Berufsfeuerwehr NRW

Eigenständige, responsive Polizei-Webseite für den fiktiven Roleplay-Server Berufsfeuerwehr NRW.

## Veröffentlichung ausschließlich über GitHub Pages

Repository: https://github.com/buhntech-dev/Polizei-WEB

1. Öffne Settings → Pages im Repository.
2. Wähle als Quelle GitHub Actions.
3. Der Workflow .github/workflows/pages.yml veröffentlicht die Seite automatisch bei jedem Push auf main.
4. Die Website-Adresse lautet danach https://buhntech-dev.github.io/Polizei-WEB/.

## Einmalige Backend-Verbindung

Die Webseite liegt auf GitHub Pages. Anmeldung, Rollenprüfung und Datenspeicherung laufen über das vorhandene Bot-Backend auf Railway. In Railway beim Bot-Service diese Variablen ergänzen:

- POLICE_WEB_URL=https://buhntech-dev.github.io/Polizei-WEB
- POLICE_REDIRECT_URI=https://berufsfeuerwehr-nrw-production.up.railway.app/police/auth/callback

Im Discord Developer Portal unter OAuth2 → Redirects exakt diese Callback-Adresse hinzufügen:
https://berufsfeuerwehr-nrw-production.up.railway.app/police/auth/callback

Die Discord-Client-ID und das Client-Secret bleiben ausschließlich auf Railway und gehören niemals in diese GitHub-Webseite.

Im Bot-Dashboard muss die Polizei-Rolle ausgewählt sein. Der Backend-Zugriff wird bei jedem API-Aufruf erneut anhand dieser Discord-Rolle geprüft.

## Funktionen

- Discord-Anmeldung für Polizeikräfte
- Serverseitige Prüfung der Polizei-Rolle
- Einwohnerregister mit Suche nach Name, Adresse und Aktenzeichen
- RP-Einwohner erfassen, bearbeiten und löschen
- Responsive Oberfläche für Desktop, Tablet und Smartphone
- Keine Discord-Secrets im Frontend

Wichtig: Nur erfundene RP-Daten eintragen. GitHub Pages hostet die Oberfläche; vertrauliche Daten werden nicht in GitHub gespeichert.