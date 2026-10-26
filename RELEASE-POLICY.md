# Release-Regeln

Dieses Repository ist öffentlich. Nur freigegebene, signierte Binärdateien und zugehörige signierte Manifeste dürfen hier veröffentlicht werden.

## Release-Assets

Für jede freigegebene Version `X.Y.Z.W`:

- `SecurityControl-Setup-X.Y.Z.W-Windows.exe`
- `SecurityControl-X.Y.Z.W-macOS-app.zip`
- `manifest-windows.json`
- `manifest-macos.json`
- `SHA256SUMS.txt`

## Signaturformat

Jedes Manifest ist ein JSON-Objekt mit `payload` und `signature`. `signature` ist Base64-kodiertes Ed25519 über die UTF-8-Bytes von `json.dumps(payload, sort_keys=True, separators=(',', ':'), ensure_ascii=False)`.

Payload enthält exakt:
- `version`: vierteilige Versionsnummer
- `platform`: `windows-x64` oder `macos-universal`
- `url`: direkte HTTPS-Downloadadresse des Pakets
- `sha256`: SHA-256 des Pakets (kleingeschrieben)
- `size`: Dateigröße in Bytes

Die Client-Anwendung muss den **öffentlichen** Schlüssel vor der Freigabe fest eingebaut bekommen. Der **private** Signaturschlüssel gehört niemals in dieses Repository, eine öffentliche GitHub Action oder ein Installationspaket.

## Noch nicht aktiv

Das derzeitige Desktop-Update-System ist absichtlich deaktiviert. Es fehlen die Freigabe eines vertrauenswürdigen Herausgebers und die Codesignierung/Notarisierung der Installationspakete. Keine unsignierten CI-Artefakte als automatisch installierbare Updates anbieten.

Vor Aktivierung: Update- und Rollback-Tests mit geschlossenen und offenen Schichten, Archivprüfung, Sicherheitsbackup und Datenbankmigrationen auf Windows und macOS durchführen.
