Session: <https://meet.google.com/zjz-bdfn-maq>

# Warum macht man das überhaupt?

* Natürlich weiß ja jeder, dass ein Backup nicht auf dem gleichen Server oder gar in der gleichen Webseite liegen (bleiben) soll.
* Daher sollte man die Daten auslagern.
* Neben S3 von Amazon gibt es auch Ionos S3 Speicher.
  * Sicherer, aber auch teurer
* Vorteile der Hetzner Storagebox
  * Stumpfer Speicher, keine Unterschiede ob Glacier u.a.
  * sehr günstig!
  * super leicht zu bedienen.
* Nachteil:
  * Nicht so sicher wie S3.

# Was wird benötigt:

* Eine Joomla! Installation
* Akeeba Backup Pro (weil Sicherung per FTP abgelegt werden muss)
  * <https://www.akeeba.com/products/akeeba-backup.html>
* Hetzner Storage Box
  * <https://www.hetzner.com/de/storage/storage-box>
* FTP-Programm (z.B. FileZilla - SSH ist auch möglich)

# Wie geht das?

1. Alle Zugangsdaten bereit legen.
2. Storage konfigurieren
   1. per Root-Account auf den Storage und ein Unterverzeichnis anlegen
   2. Beim Hetzner Robot einloggen einen SUB-Account anlegen und die Zugangsdaten merken!! Die werden nur 1x angezeigt und werden dann neu vergeben. Ändern des PW nicht möglich.
   3. Externe Erreichbarkeit aktivieren
3. Akeeba Backup konfigurieren
   * neues Sicherungsprofil anlegen
   * Post-Processing - Remote FTP / SSH (je nachdem was man möchte)
   * Splitsize 20MB ist für mich ein guter Wert. Diese Einstellung kann individuell abweichen
   * Jedes Teil sofort bearbeiten / wegschicken (Process each part immediately)
   * danach sofort löschen (Delete archive after processing)
   * SSH
   * FTP-Daten eintragen
     * Achtung: gesicherte Verbindung ABSTELLEN, sonst geht es nicht (zumindest bei mir).
4. (BM einrichten)

# BackupMonkey - Eine Vorstellung

* Anleitung gibt es schon: <https://backupmonkey.io/de/blog/45-leitfaden-sichere-speicherung-von-akeeba-backups-in-einer-hetzner-storage-box>
  * Folgt bei nik-o-mat - nach dem Relaunch.