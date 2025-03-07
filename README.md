# whisper-colab-drive-transcribe:
**Worst name ever!**

## Description

This Python script for Google Colab automates the batch transcription of Italian audio files using OpenAI's Whisper model. Audio files are processed directly from Google Drive, and the resulting transcriptions are saved as text files in the same folder.

### Main Features

- Batch Transcription: Automatically processes multiple audio files in sequence.
- Organized File Management: Relies on a specific file naming structure to organize transcriptions.
- Flexible Lesson Identifiers: Allows the use of both numbers and dates (or any string without dots ".") as lesson identifiers.
- Google Drive Integration: Directly accesses audio files and saves transcriptions to Google Drive.
- Resumption from Interruptions: Able to resume transcriptions even if the process is interrupted.

### Variable Description

- `model_name`: Specifies the Whisper model to use ("tiny", "base", "small", "medium", "large"). Larger models offer greater accuracy but require more time and resources.
- `lang`: Sets the audio file language to "it" (Italian).
- `in_folder`: Path on Google Drive where the audio files to be transcribed are located.
- `out_folder`: Path on Google Drive where the transcriptions will be saved.

### Audio File Structure

Audio files must be organized in the `in_folder` folder using the following naming convention:

`<lesson_identifier>.<recording_number>.<extension>`

Where `<lesson_identifier>` can be a number or a date (or any string without dots ".").

#### Examples:

- `1.1.m4a` (first recording of lesson 1)
- `2023-10-27.1.mp3` (first recording of the lesson from October 27, 2023)
- `AdvancedCourse.2.wav` (second recording of the AdvancedCourse lesson)

### Transcription Structure

Transcriptions are saved in the `out_folder` folder using the following naming convention:

`<lesson_identifier>.txt`

#### Examples:

- `1.txt` (contains the transcription of 1.1.m4a)
- `2023-10-27.txt` (contains the transcription of 2023-10-27.1.mp3)
- `AdvancedCourse.txt` (contains the transcription of AdvancedCourse.2.wav)

### Implementation Details

- Dependency Installation:
  - Installs the `openai-whisper` and `ffmpeg` libraries.
- Google Drive Mounting:
    - Mounts Google Drive to access audio files and save transcriptions.
- Whisper Model Loading:
    - Loads the specified Whisper model.
- Existing Transcription Management:
    - Scans the output folder to identify already transcribed lessons, avoiding duplicates.
- Audio File Processing:
    - Iterates through the audio files in the input folder.
    - Checks if the lesson has already been transcribed.
    - Transcribes the audio files using the Whisper model.
    - Handles any errors during transcription.
    - Saves transcriptions to the corresponding text files.
- Status Output:
    - Prints informative messages during processing to monitor the status.
## Descrizione
Questo script Python per Google Colab automatizza la trascrizione batch di file audio in italiano utilizzando il modello Whisper di OpenAI. I file audio vengono elaborati direttamente da Google Drive, e le trascrizioni risultanti sono salvate come file di testo nella stessa cartella.

### Caratteristiche Principali

- Trascrizione Batch: Elabora automaticamente più file audio in sequenza.
- Gestione di File Organizzati: Si basa su una struttura di nomi di file specifica per organizzare le trascrizioni.
- Identificatori di Lezione Flessibili: Permette di utilizzare sia numeri che date (o qualsiasi altra stringa senza punti ".") come identificatori di lezione.
- Integrazione con Google Drive: Accede direttamente ai file audio e salva le trascrizioni su Google Drive.
- Ripresa da Interruzioni: è in grado di riprendere le trascrizioni anche se il processo viene interrotto.

### Descrizione delle Variabili

- `model_name`: Specifica il modello Whisper da utilizzare ("tiny", "base", "small", "medium", "large"). Modelli più grandi offrono maggiore accuratezza, ma richiedono più tempo e risorse.
- `lang`: Imposta la lingua dei file audio su "it" (italiano).
- `in_folder`: Percorso su Google Drive dove si trovano i file audio da trascrivere.
- `out_folder`: Percorso su Google Drive dove verranno salvate le trascrizioni.

### Struttura dei File Audio

I file audio devono essere organizzati nella cartella in_folder con la seguente convenzione di denominazione:

<identificatore_lezione>.<numero_registrazione>.<estensione>

Dove <identificatore_lezione> può essere un numero o una data (o qualsiasi stringa senza punti ".").

#### Esempi:

- `1.1.m4a` (prima registrazione della lezione 1)
- '2023-10-27.1.mp3` (prima registrazione della lezione del 27 ottobre 2023)
- `CorsoAvanzato.2.wav` (seconda registrazione della lezione CorsoAvanzato)

### Struttura delle Trascrizioni:

Le trascrizioni vengono salvate nella cartella out_folder con la seguente convenzione di denominazione:

<identificatore_lezione>.txt

#### Esempi:

- `1.txt` (contiene la trascrizione di 1.1.m4a)
- `2023-10-27.txt` (contiene la trascrizione di 2023-10-27.1.mp3)
- `CorsoAvanzato.txt` (contiene la trascrizione di CorsoAvanzato.2.wav)

### Dettagli Implementativi
- Installazione delle Dipendenze:
  - Installa le librerie openai-whisper e ffmpeg.
- Montaggio di Google Drive:
    - Monta Google Drive per accedere ai file audio e salvare le trascrizioni.
- Caricamento del Modello Whisper:
    - Carica il modello Whisper specificato.
- Gestione delle Trascrizioni Esistenti:
    - Scansiona la cartella di output per identificare le lezioni già trascritte, in modo da evitare duplicati.
- Elaborazione dei File Audio:
    - Itera attraverso i file audio nella cartella di input.
    - Controlla se la lezione è già stata trascritta.
    - Trascrive i file audio utilizzando il modello Whisper.
    - Gestisce eventuali errori durante la trascrizione.
    - Salva le trascrizioni nei file di testo corrispondenti.
- Output di Stato:
    - Stampa messaggi informativi durante l'elaborazione per monitorare lo stato.
