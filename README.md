# Swiftie-Quiz

Ein Musik-Quiz für den Unterricht: 15 Fragen rund um Taylor Swift, ihre Karriere und ein bisschen Songaufbau (Strophe, Refrain, Bridge …).

**Zur Seite:** https://greenboy87.github.io/swiftie-quiz/

## Spielmodi

| Modus | Wofür | Bedienung |
|---|---|---|
| **Beamer** (Standard) | Lehrkraft klickt sich vor der Klasse durch, die Klasse zeigt die Antwort mit Fingern (1 = A … 4 = D) | Klick oder Tasten `1`–`4` / `A`–`D` wählen, `Leertaste` oder `→` = auflösen bzw. weiter |
| **Teams** | 2–4 Teams mit Punktestand; nach jeder Frage antippen, welche Teams richtig lagen | wie Beamer, danach Team-Buttons antippen |
| **iPad** | Kinder spielen allein (Hoch- und Querformat), am Ende Punktzahl + Swiftie-Level | Antwort antippen, dann „Weiter“ |

Der QR-Code auf dem Startbildschirm führt direkt in den iPad-Modus. Er wird in der Seite selbst erzeugt, ohne externen Dienst.

Optional gibt es einen 20-Sekunden-Timer: kein Ticken, nur ein kurzer Ton am Ende.

**Swiftie-Level:** 0–5 Newcomer · 6–10 Fan · 11–13 Swiftie · 14–15 Mastermind

## Fragen ändern

Alles steckt in **einer Datei**: `index.html`. Ganz oben steht die Liste `FRAGEN`:

```js
{
  frage: "Welche Zahl gilt als ihre Glückszahl?",
  antworten: ["7", "13", "21", "99"],
  richtig: 1,            // 0 = erste, 1 = zweite, 2 = dritte, 3 = vierte Antwort
  erklaerung: "Die 13 – sie hat am 13. Dezember Geburtstag."
},
```

- Immer genau **4 Antworten**. Die Reihenfolge wird beim Spielen automatisch gemischt, du kannst also die richtige Antwort an jede Stelle schreiben.
- `richtig` zählt **ab 0**.
- Fragen hinzufügen oder löschen geht einfach so. Fortschrittsanzeige und Level-Grenzen passen sich an die Anzahl an.
- Texte für die Level stehen direkt darunter in `LEVELS`, die Timer-Länge in `TIMER_SEKUNDEN`.

Bearbeiten geht direkt auf GitHub (Datei öffnen → Stift-Symbol → „Commit changes“). Nach ein bis zwei Minuten ist die Seite aktualisiert.

## Lokal ausprobieren

```bash
python3 -m http.server 8000
```

Dann im Browser `http://localhost:8000` öffnen. Es geht auch ohne Server: einfach `index.html` doppelklicken.

## Rechte & Datenschutz

- Keine Songtexte, keine Musik, keine Fotos, keine Cover oder Logos. Alle Texte sind selbst geschrieben, alle Grafiken sind mit CSS/SVG gezeichnet.
- Keine Namenseingabe, kein Tracking, keine Cookies, kein Speichern. Eine Content-Security-Policy in der Seite blockiert zusätzlich jede Datenübertragung.
- Einzige externe Quelle ist die Schrift „Poppins“ von Google Fonts. Ohne Internet wird automatisch die Systemschrift genutzt, das Quiz läuft trotzdem komplett.

Dies ist ein Fan-Quiz für den Unterricht und steht in keiner Verbindung zu Taylor Swift oder ihrem Label.
