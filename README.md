# SecurityControl – Offizieller Update-Kanal

Dieses öffentliche Repository dient ausschließlich zur Verteilung freigegebener Updates der Desktop-Anwendung **SecurityControl**.

**Der Quellcode bleibt privat** im separaten Repository `securitycontrol-dev/SecurityControl`.

## Veröffentlichungen

Neue Versionen erscheinen später unter [Releases](https://github.com/securitycontrol-dev/SecurityControl-Updates/releases).

Eine freigegebene Version kann enthalten:

- Windows-Installationspaket (`.exe`)
- macOS-Anwendungspaket (`.zip`)
- signierte Update-Manifeste für Windows und macOS
- SHA-256-Prüfsummen
- Versionshinweise

## Update-Verfahren ohne Apple-Developer-Account

- **Windows:** geprüfte Updates werden bei geschlossenem Server und ohne offene Schichten nach verifizierter Sicherheitskopie automatisch installiert, sofern Windows die Ausführung zulässt. Ohne Codesignatur sind Sicherheitswarnungen möglich.
- **macOS:** Updateprüfung und verifizierter Download; Installation bewusst manuell. Eine nicht notarisierte App kann durch Gatekeeper blockiert werden.
- **Beide Systeme:** Noch kein aktiver Update-Feed. Erst nach Einrichtung einer vertrauenswürdigen Release-Signatur und Prüfung der veröffentlichten Pakete wird die Updatefunktion aktiviert.

## Sicherheit

- Keine Quellcodes, Passwörter, Datenbanken, personenbezogenen Daten oder privaten Signaturschlüssel hier veröffentlichen.
- Ein erfolgreiches CI-Build bedeutet **nicht**, dass eine Version für automatische Updates freigegeben ist.
- Die Anwendung akzeptiert Updates erst nach Überprüfung einer gültigen Ed25519-Signatur und des SHA-256-Hashes.
- Installationen bei offenen Schichten oder laufendem Server sind gesperrt. Vor der Installation wird eine separate verschlüsselte Sicherheitskopie geprüft.
- Bis signierte und betriebssystemseitig vertrauenswürdige Pakete bereitstehen, bleibt der automatische Update-Kanal deaktiviert.

**Status:** Update-Kanal vorbereitet; noch keine für automatische Installation freigegebene Version.
