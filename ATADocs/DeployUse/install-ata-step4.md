---
# required metadata

title: Installieren von ATA – Schritt 4 | Microsoft Advanced Threat Analytics
description: Im vierten Schritt beim Installieren von ATA installieren Sie das ATA-Gateway.
keywords:
author: rkarlin
manager: stevenpo
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: identity-ata
ms.service: advanced-threat-analytics
ms.technology: security
ms.assetid: 6bbc50c3-bfa8-41db-a2f9-56eed68ef5d2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: bennyl
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Installieren von ATA – Schritt 4

>[!div class="step-by-step"]
[« Schritt 3](install-ata-step3.md)
[Schritt 5 »](install-ata-step5.md)

## Schritt 4: Installieren des ATA-Gateways
Überprüfen Sie vor der Installation des ATA-Gateways, ob die Portspiegelung ordnungsgemäß konfiguriert ist und ob das ATA-Gateway Datenverkehr zu und von den Domänencontrollern anzeigen kann. Weitere Informationen finden Sie unter [Überprüfen der Portspiegelung](/advanced-threat-analytics/plandesign/validate-port-mirroring).

> [!IMPORTANT]
> Stellen Sie sicher, dass [KB2919355](http://support.microsoft.com/kb/2919355/) installiert wurde.  Führen Sie das folgende PowerShell-Cmdlet aus, um zu überprüfen, ob der Hotfix installiert ist:
>
> `Get-HotFix -Id kb2919355`

Führen Sie die folgenden Schritte auf dem ATA-Gatewayserver aus.

1.  Extrahieren Sie die Dateien aus der ZIP-Datei.

2.  Führen Sie „Microsoft ATA Gateway Setup.exe“ an einer Eingabeaufforderung mit erhöhten Rechten aus, und befolgen Sie die Anweisungen des Setup-Assistenten.

3.  Wählen Sie auf der Seite **Willkommen** Ihre Sprache aus, und klicken Sie auf **Weiter**.

4.  Geben Sie unter **ATA-Gatewaykonfiguration** basierend auf Ihrer Umgebung die folgenden Informationen ein:

    ![Abbildung ATA-Gatewaykonfiguration](media/ATA-Gateway-Configuration.JPG)

    |Feld|Beschreibung|Kommentare|
    |---------|---------------|------------|
    |Installationspfad|Dies ist der Speicherort, an dem das ATA-Gateway installiert wird. Standardmäßig ist dies „%programfiles%\Microsoft Advanced Threat Analytics\Gateway“.|Behalten Sie den Standardwert bei.|
    |SSL-Zertifikat für ATA-Gatewaydienst|Dies ist das Zertifikat, das vom ATA-Gateway verwendet wird.|Verwenden Sie ein selbstsigniertes Zertifikat nur für Testumgebungen.|
    |ATA-Gatewayregistrierung|Geben Sie den Benutzernamen und das Kennwort des ATA-Administrators ein.|Um das ATA-Gateway bei ATA Center zu registrieren, geben Sie den Benutzernamen und das Kennwort des Benutzers ein, der ATA Center installiert hat. Dieser Benutzer muss Mitglied einer der folgenden lokalen Gruppen in ATA Center sein.<br /><br />- Administratoren<br />- Microsoft Advanced Threat Analytics-Administratoren **Hinweis:** Diese Anmeldeinformationen werden nur für die Registrierung verwendet und nicht in ATA gespeichert.|
    Bei der Installation des ATA-Gateways werden die folgenden Komponenten installiert und konfiguriert:

    -   KB3047154

        > [!IMPORTANT]
        > -   Installieren Sie KB3047154 nicht auf einem Virtualisierungshost. Dies kann dazu führen, dass die Portspiegelung nicht mehr ordnungsgemäß ausgeführt wird.
        > -   Installieren Sie Message Analyzer, Wireshark oder andere Software zur Netzwerkerfassung nicht auf dem ATA-Gateway. Wenn Sie den Netzwerkverkehr erfassen möchten, installieren und verwenden Sie Microsoft Network Monitor 3.4.

    -   ATA-Gatewaydienst

    -   Microsoft Visual C++ 2013 Redistributable

    -   Benutzerdefinierter Systemmonitor-Datensammlungssatz

5.  Klicken Sie nach Abschluss der Installation auf **Starten**, um den Browser zu öffnen und sich in der ATA-Konsole anzumelden.


>[!div class="step-by-step"]
[« Schritt 3](install-ata-step3.md)
[Schritt 5 »](install-ata-step5.md)

## Siehe auch

- [Unterstützung finden Sie in unserem Forum.](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)
- [Konfigurieren der Ereignissammlung](/advanced-threat-analytics/plandesign/configure-event-collection)
- [Voraussetzungen für ATA](/advanced-threat-analytics/plandesign/ata-prerequisites)


<!--HONumber=Apr16_HO2-->


