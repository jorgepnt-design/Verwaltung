# AccountVerwaltung

Eine mobilefreundliche Web-App zur Verwaltung von Kunden-Accounts, Zugangsdaten und Ablaufdaten.

## Funktionen

- Verschlüsselter lokaler Tresor mit Master-Passwort
- AES-GCM-Verschlüsselung, Schlüsselableitung mit PBKDF2 (250.000 Iterationen)
- Kunden, Services, URLs, Benutzernamen, Passwörter und Notizen verwalten
- Suche und Statusfilter
- Automatische Einstufung in aktiv, bald fällig und abgelaufen
- Erinnerungszeiträume pro Account
- Verschlüsseltes Backup exportieren
- Responsive Oberfläche für Smartphone, Tablet und Desktop

## Starten

Da keine Build-Werkzeuge benötigt werden, kann `index.html` direkt geöffnet oder das Verzeichnis über einen einfachen Webserver ausgeliefert werden:

```bash
python3 -m http.server 8080
```

Danach `http://localhost:8080` aufrufen.

## Sicherheit und Datenhaltung

Alle Accountdaten werden vor dem Speichern im Browser mit AES-GCM verschlüsselt. Das Master-Passwort und der daraus abgeleitete Schlüssel werden nicht gespeichert. Die Daten verbleiben im lokalen Browser (`localStorage`). Deshalb sollte regelmäßig ein verschlüsseltes Backup exportiert werden.

Diese Version ist als persönlicher, lokaler Tresor gedacht. Für mehrere Benutzer, geräteübergreifende Synchronisierung, serverseitige Rollen oder E-Mail-Erinnerungen ist ein zusätzliches Backend erforderlich.
