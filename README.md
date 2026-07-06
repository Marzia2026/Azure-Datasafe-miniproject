# Azure-Datasafe-miniproject

## Azure – Backup, Recovery & Replication


---

# A1 – Infrastruktur erstellen

Folgende Ressourcen wurden erfolgreich erstellt:

- Resource Group: **rg-datasafe**
- Virtuelle Maschine: **vm-datasafe01**
  - Ubuntu Server 22.04 LTS
  - Größe: B2ats v2
  - OS-Disk: Standard HDD
- Storage Account: **stdatasafe...**
- Azure File Share: **backup-share**

Die virtuelle Maschine wurde erfolgreich erstellt und befand sich im Status **Running**.

---

# A2 – Recovery Services Vault

Ein Recovery Services Vault mit dem Namen **rsv-datasafe** wurde in derselben Region wie die VM erstellt.

Der Vault dient als zentrale Verwaltung für:

- Azure Backup
- Azure Site Recovery

---

# A3 – Azure Backup

Für die virtuelle Maschine wurde Azure Backup aktiviert.

Konfiguration:

- Workload: Azure Virtual Machine
- Backup Policy: Daily
- Aufbewahrung: 7 Tage

Anschließend wurde ein manueller Backup-Job gestartet und erfolgreich ausgeführt.

---

# A4 – Azure Files Backup

Für die Azure File Share **backup-share** wurde ebenfalls Azure Backup eingerichtet.

Zusätzlich wurden zwei Testdateien hochgeladen:

- test1.txt
- test2.txt

Die File Share wurde erfolgreich als Backup-Quelle geschützt.

---

# A5 – Azure Site Recovery

Für die virtuelle Maschine wurde Azure Site Recovery eingerichtet.

Dabei wurde:

- eine Zielregion ausgewählt,
- die Replikation aktiviert,
- ein Automation Account erstellt,
- und die Replikation erfolgreich gestartet.

Der Replikationsstatus wurde anschließend als **Healthy** angezeigt.

Ein Failover wurde nicht durchgeführt.

---

# Aufräumen der Ressourcen

Nach Abschluss des Projekts wurden alle Ressourcen gelöscht:

- Disable Replication
- Backup stoppen und Backup-Daten löschen
- Recovery Services Vault löschen
- ASR-Vault in der Zielregion löschen
- Resource Group **rg-datasafe** löschen

Dadurch entstehen keine weiteren Azure-Kosten.

---

# Fazit

In diesem Projekt wurde erfolgreich eine Azure-Umgebung aufgebaut und mit Azure Backup sowie Azure Site Recovery abgesichert.

Dabei wurden die Unterschiede zwischen Backup und Disaster Recovery praktisch kennengelernt:

- **Azure Backup** dient zur Wiederherstellung von Daten.
- **Azure Site Recovery** ermöglicht den Weiterbetrieb einer VM bei einem Ausfall der primären Region.

Das Projekt wurde erfolgreich abgeschlossen.
