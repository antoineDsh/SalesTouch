# SalesTouch

[English](../README.md) · [Français](fr.md) · [Deutsch](de.md) · [Español](es.md) · [Português](pt.md) · [Italiano](it.md)

**LinkedIn-Akquise für KI-Agenten.** SalesTouch ist ein LinkedIn MCP, das Claude mit Interessentenrecherche, Unterhaltungen, Nachrichten, Beiträgen, Nachfassaktionen und Warteschlangen verbindet. SalesTouch ist weder mit LinkedIn verbunden noch von LinkedIn bestätigt.

## Voraussetzungen

Ein SalesTouch-Arbeitsbereich mit aktivem Tarif und verbundenem LinkedIn-Konto. Für Sales Navigator benötigen Sie die entsprechenden Zugriffsrechte. Ergebnisse hängen von Berechtigungen, verfügbaren Daten und Plattformlimits ab.

## In Claude Code installieren

Führen Sie in Claude Code Folgendes aus:

```text
/plugin marketplace add antoineDsh/SalesTouch
/plugin install salestouch@salestouch
```

Starten Sie Claude Code neu, führen Sie `/mcp` aus, wählen Sie SalesTouch und autorisieren Sie die Verbindung im Browser. LinkedIn-Passwörter, Cookies und API-Schlüssel gehören weder in die Unterhaltung noch in die Plugin-Konfiguration.

## In Claude Desktop oder Cowork installieren

Öffnen Sie **Customize → Plugins**. Wählen Sie unter **Personal plugins** die Option **+ → Add marketplace**, dann die Repository-Option und geben Sie `antoineDsh/SalesTouch` ein. Installieren und aktivieren Sie `salestouch` und autorisieren Sie den SalesTouch-Connector. Die verfügbaren Optionen hängen vom Claude-Tarif und den Einstellungen Ihrer Organisation ab.

## Drei erste Prompts

1. „Liste meine verbundenen LinkedIn-Konten mit SalesTouch auf.“
2. „Recherchiere dieses LinkedIn-Profil und seine neuesten Beiträge. Entwirf eine passende erste Nachricht, ohne sie zu senden: [Profil-URL].“
3. „Lies diese LinkedIn-Unterhaltung, fasse die Bedürfnisse des Interessenten zusammen und entwirf eine Antwort, ohne sie zu senden: [Unterhaltungs-ID oder Profil-URL].“

Ersetzen Sie die Platzhalter durch Ihre Ziele. Sie können auch Suchergebnisse oder Personen aus Beitragsinteraktionen extrahieren, gespeicherte Ergebnisse durchblättern und Exporte herunterladen. Prüfen Sie Empfänger, Inhalt und Zeitpunkt vor der Freigabe einer Aktion. Ausstehende Aktionen sind noch nicht zugestellt. Prüfen Sie die Warteschlange, bevor Sie einen Schreibvorgang wiederholen.

## Verbindung und Hilfe

Der entfernte MCP-Endpunkt ist `https://www.salestouch.io/api/mcp`, mit Streamable HTTP und OAuth. Bei Problemen verbinden Sie den Connector erneut, prüfen Arbeitsbereich und LinkedIn-Verbindung und wiederholen die Kontoabfrage. Senden Sie dem Support nur einen unkritischen Fehlercode und Schritte zur Reproduktion, keine Zugangsdaten, Tokens oder privaten Nachrichten.

[Einrichtung](../SETUP.md) · [Support](https://www.salestouch.io/support) · [Sicherheit](../SECURITY.md) · [Dokumentation](https://www.salestouch.io/docs) · [Datenschutz](https://www.salestouch.io/privacy) · [Bedingungen](https://www.salestouch.io/terms) · [support@salestouch.io](mailto:support@salestouch.io)

Die Plugin-Dateien stehen unter der [MIT-Lizenz](../LICENSE). Das gehostete Backend ist proprietär.

## Version 0.9.1

Aktualisierte Installationshilfe in sechs Sprachen; Einrichtung und Support im Paket; technische MCP-Analysen ohne Gesprächsziele oder Inhalte der Tool-Aufrufe. [Änderungsverlauf](../CHANGELOG.md).
