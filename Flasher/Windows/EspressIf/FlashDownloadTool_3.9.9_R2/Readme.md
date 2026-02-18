# ESP32 Merge-Bin mit Espressif Flash Tool flashen

Diese Anleitung beschreibt, wie eine **Firmware (.bin)** Datei auf einen ESP32 mit dem offiziellen **Espressif Flash Download Tool** geflasht wird.

---

## Voraussetzungen

- Windows PC  
- USB-Kabel (Datenkabel, kein reines Ladekabel)
- Installierte USB-Treiber (CP210x oder CH340 je nach Board)
- Espressif Flash Download Tool
- Merge-Bin Datei (z. B. `esp32s3_blink.bin`)

---

## 1. Flash Tool herunterladen

Das offizielle Tool kann hier heruntergeladen werden:

flash_download_tool_3.9.9_R2.exe

Lade die aktuelle Version des **Flash Download Tool** für Windows herunter.

---

## 2. ESP32 verbinden

1. ESP32 per USB anschließen  
2. Im Geräte-Manager prüfen, welcher **COM-Port** verwendet wird  

---

## 3. Flash Download Tool starten

1. `flash_download_tool.exe` starten  
2. Chip auswählen (z. B. **ESP32**, **ESP32-S3**, **ESP32-C3**, je nach Board**)  
3. Auf **OK** klicken  

---

## 4. Firmware konfigurieren

Da es sich um eine **Merge-Binary** handelt:

1. Im oberen Bereich die `.bin` Datei auswählen  
2. Als **Adresse** `0x0000` eintragen  
3. Häkchen aktivieren  

Beispiel: esp32s3_blink.bin 0x0000


---

## 5. Flash Einstellungen

Typische Einstellungen:

- SPI Speed: 40MHz  
- SPI Mode: DIO  
- Flash Size: passend zum Modul (z. B. 4MB, 8MB, 16MB)  
- COM-Port auswählen  
- Baudrate: 115200 oder 921600  

---

## 6. Flash-Vorgang starten

1. Falls nötig: **BOOT-Taste gedrückt halten**
2. Auf **START** klicken  
3. BOOT-Taste loslassen, sobald der Upload beginnt  

Wenn alles korrekt ist, erscheint: FINISH


---

## 7. Neustart

Nach erfolgreichem Flash:

- ESP32 Reset-Taste drücken  
oder  
- USB kurz abziehen und neu verbinden  

---

## Troubleshooting

### Sync-Fehler
- BOOT-Taste gedrückt halten beim Start
- Anderen USB-Port probieren
- Anderes USB-Kabel testen

### Falsche Flash Size
Wenn das Programm nicht startet, stimmt möglicherweise die Flash-Größe nicht.

---


