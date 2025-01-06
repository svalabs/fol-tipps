# fol-tipps

Eine kleine Webseite, die mittels [DataTables](https://datatables.net/) die Tool- und Medientipps des [FOCUS ON: Linux](https://focusonlinux.podigee.io/)-Podcasts anzeigt. Durchsuchbar.

## Benutzung

Einfach die Webseite mit einem kleinen Webserver starten, z.B. [Python `http.server`](https://docs.python.org/3/library/http.html):

```command
$ python3 -m http.server
```

## Datenpflege

Tooltipps werden in der Datei [`data.txt`](data.txt) gepflegt - diese besteht aus einem Array mit unzähligen Datensätzen im folgenden Format:

```json
{
    "episode": "E19",
    "episode_title": "Newsupdate 12/22 - Linux 6.1, ComposeFS, Proxmox 7.3, Forgejo, ClamAV 1.0",
    "episode_url": "https://focusonlinux.podigee.io/43-newsupdate-12-22-linux-6-1-composefs-proxmox-7-3-forgejo-clamav-1-0",
    "date": "2022-12-23",
    "name": "jo",
    "description": "JSON output from a shell",
    "url": "https://github.com/jpmens/jo",
    "author": "Christian Stankowic"
},
```

| Feld | Erklärung |
| ---- | --------- |
| `episode` | Kurzname der Episode (*z.B. `E19`*) |
| `episode_title` | Vollständiger Titel der Episode |
| `episode_url` | URL zur Episode auf **Podigee** |
| `date` | Datum der Veröffentlichung im Format `YYYY-MM-DD` |
| `name` | Name des Tool- oder Medientipps |
| `type` | Typ des Tipps: Tooltipp (💿), Webseite (🌍), Buch/Artikel (📕), Video (🎥) oder Podcast (🎧) |
| `description` | **Kurze** Beschreibung des Tooltipps, kann meist der Webseite entnommen und gekürzt werden. Kein vollständiger Satz, kurz und prägnant. |
| `url` | URL zur Webseite |
| `author` | Person, die den Tipp vorgestellt hat |
