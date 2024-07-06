# yt-transkript - YouTube Transcript Downloader

## Language Selection / Sprachauswahl
- [English](#english)
- [Deutsch](#deutsch)

## English
### Description
This Bash script allows you to automatically download the transcript of a YouTube video without downloading the video itself. It uses the command-line tool `yt-dlp` to extract the video's subtitles.

### Usage
The Bash script allows for automatic-downloading of the transcript of a YouTube video without downloading the video itself. Use the following call formats:

```bash
yt-transkript [options] URL output_file

yt-transkript -l en URL output_file

yt-transkript [--version|-V|-#|]
yt-transkript [--help|-h|--hilf]
```

#### Available options include

- `-l`: Set output language (E.g., 'en' for English. If not set, German subtitles will be downloaded.).
- `-t`: Set download file format by file extension. (default is 'ttml'; only alternative value: 'vtt'). Normally, you do not need to specify this parameter because the script automatically selects an available one of these two subtitle file formats. TTML is the much more efficient choice for this script, choosing the VTT format slows down the script.

**Get self-descriptions of the script:**

- `-h`: Display the help page.
- `#`: Display the version of $SCRIPT_NAME.

**Attention**: The script cleans the subtitle file to enhance text readability

### Dependencies

- `yt-dlp` (command line tool for downloading videos and subtitles)

### Functionality
1. The script creates a temporary file to store the downloaded subtitles.

2. Using yt-dlp, the subtitles are downloaded in TTML format in English if you use the option `-l en` or in another language specified with the `-l` parameter. 

    - If no output language is specified, it will default to German. 
    - If the download in TTML format fails, the script will attempt to download the subtitles in VTT format.

3. Basic data about the video is included at the start of the output file:

    - Video title
    - Video URL
    - YouTube channel
    - Upload date to YouTube
    
4. Once the subtitles are successfully downloaded, they undergo cleaning:

    - The first three lines are removed.
    - HTML tags like `<c>`, timestamps like `<00:00:00.840>` and time interval data like `00:00:00.160 --> 00:00:02.430` are removed.
    - Empty lines are removed and consecutive identical lines are consolidated into one line.

5. The cleaned transcript file is saved in the specified output file. If no output file is specified, the transcript is saved under the filename `transcript.txt` in the current working directory.

6. Temporary files are deleted.

### Error handling
If the subtitle file is not found or an error occurs during the download, the script will print an error message and exit with a non-zero status code.

### Author
Bernd Storck

### Contact
**Facebook Group:** [Linux mit Bernd Storck](https://www.facebook.com/groups/164934964047448)

### License
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but **without any warranty**; without even the implied warranty of merchantability or fitness for a particular purpose. See the GNU General Public License for more details.

You will find the GNU General Public License at <http://www.gnu.org/licenses/>.


## Deutsch
### Beschreibung
Dieses Bash-Skript ermöglicht es Ihnen automatisch, das Transkript eines YouTube-Videos herunterzuladen, ohne das Video selbst herunterzuladen. Es verwendet das Kommandozeilentool `yt-dlp` zur Extraktion der Untertitel.

### Verwendung
Das Bash-Skript ermöglicht das automatische Herunterladen des Transkripts eines YouTube-Videos, ohne das Video selbst herunterzuladen. Verwenden Sie die folgenden Befehlsformate:

```bash
yt-transkript [Optionen] URL Ausgabedatei

yt-transkript [--version|-V|-#]
yt-transkript [--hilf|--help|-h]
```

#### Folgende Optionen sind verfügbar:

- `-l`: Ausgabesprache festlegen (Z.B. "en" für Englisch. Um deutsche Untertitel zu erhalten, ist dieser Parameter überflüssig, das Deutsch die Standardsprache für die Ausgabe der Untertitel ist.
- `-t`: Dateiformat/Dateierweiterung für den Download festlegen (Standard ist 'ttml'; einziger alternativer Wert: 'vtt').  Normalerweise müssen Sie diesen Parameter nicht angeben, da das Skript automatisch von diesen beiden Untertiteldateiformaten ein verfügbares auswählt. TTML ist die für dieses Script ungleich effizientere Wahl, d. h. die Wahl des VTT-Formats verlangsamt das Script.

**Selbstbeschreibungen des Scripts abrufen:**
- `--hilf`: Deutschsprachige Hilfe anzeigen.
- `--help`: Je nach Systemsprache deutsche oder englische Hilfe anzeigen.
- `-#`: Die Versionsnummer von $SCRIPT_NAME anzeigen.

**Bitte beachten**: Das Skript bereinigt die Untertiteldatei für eine optimale Textnutzung.

### Abhängigkeiten

- `yt-dlp` (Kommandozeilentool zum Herunterladen von Videos und Untertiteln)

### Funktionsweise

1. Das Skript erstellt eine temporäre Datei, um die heruntergeladenen Untertitel zwischenzuspeichern.

2. Mit `yt-dlp` werden die Untertitel im TTML-Format in Deutsch (Standardsprache) oder in der mit dem Parameter `-l` angegebenen Sprache heruntergeladen.  Misslingt der Download im TTML-Format, dann versucht das Script die Untertitel im VTT-Format zu holen.

3. Grundlegende Daten über das Video werden an den Anfang der Ausgabedatei geschrieben: 
    - Video-Titel
    - URL, die Web-Adresse des Videos
    - Youtube-Kanal
    - Datum des Uploads zu YouTube

4. Wenn die Untertiteldatei erfolgreich heruntergeladen wurde, wird sie bereinigt:
    - Die ersten drei Zeilen werden entfernt.
    - HTML-Tags wie `<c>`, Zeitstempel wie `<00:00:00.840>` und Angaben zu Zeitintervallen wie `00:00:00.160 --> 00:00:02.430` werden entfernt.
    - Leere Zeilen werden gelöscht und aufeinanderfolgende identische Zeilen werden zu einer Zeile reduziert.

5. Die bereinigte Transkriptdatei wird in der angegebenen Ausgabedatei gespeichert. Wurde keine Ausgabedatei angegeben, dann wird das Transkript unter dem Dateinamen `transkript.txt` im aktuellen Arbeitsverzeichnis gespeichert.

6. Temporäre Dateien werden gelöscht.

### Fehlerbehandlung

Wenn die Untertiteldatei nicht gefunden oder ein Fehler während des Downloads auftritt, gibt das Skript eine Fehlermeldung auf Deutsch aus und beendet sich mit einem Nicht-Null-Statuscode.

### Autor
Bernd Storck

### Kontakt
**Facebook-Gruppe:** [Linux mit Bernd Storck](https://www.facebook.com/groups/164934964047448)

### Lizenz
Dieses Programm ist Freie Software: Sie können es unter den Bedingungen der GNU General Public License, wie sie von der Free Software Foundation veröffentlicht wurde, weitergeben und/oder modifizieren, entweder gemäß Version 3 der Lizenz oder (nach Ihrer Option) einer späteren Version.

Dieses Programm wird **ohne jegliche Gewährleistung** bereitgestellt; auch ohne die implizite Garantie der Marktgängigkeit oder Eignung für einen bestimmten Zweck. Weitere Details finden Sie in der GNU General Public License.

Die GNU General Public License finden Sie unter <http://www.gnu.org/licenses/>.
