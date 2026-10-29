# Trading Interview Trainer

A free, browser-based practice tool for trading-assessment skills: fast visual matching and multitasking under time pressure.

> **Independent project.** This repository is not affiliated with, endorsed by, or connected to All Options or TradingInterview.com. It does not contain copied assessment questions, proprietary assets, or leaked test content. The mechanics are implemented from publicly described formats; all questions, data, and visual stimuli in this trainer are independently generated.

## What is included

### Reaction Test

- Four reference figures and one target figure.
- Press **M** when the target is identical to one of the references: same shape **and** same rotation.
- Press **Z** when there is no exact match.
- A rotated version of the same shape does **not** count as a match.
- Each stimulus expires after **2.5 seconds**.
- Training session: **5 minutes**.
- End-of-session metrics: score, accuracy, average response time, and skipped items.

The visual figures are generated locally from original SVG primitives in `index.html`.

### Multitasking Test

Two tasks run simultaneously for **10 minutes**:

1. **Duplicate-number task** — scan 10 rows of five four-digit numbers and select both copies of the duplicated value in each row. Submit the list and immediately continue with a new one.
2. **Audio-question task** — questions are spoken using the browser's built-in Web Speech API. Answers are selected from a shared 15-option grid.

Question types include:

- Phonebook lookups: profession, age, and address.
- Agenda lookups: scheduled appointments.
- Timed instructions: remember an answer and click it at the requested time while continuing the duplicate task.

The trainer deliberately keeps the audio question text off-screen during play so that the second task competes for attention.

## Run it

There are no dependencies, build tools, accounts, APIs, or backend.

1. Clone or download the repository.
2. Open `index.html` in a modern browser.
3. Use **Chrome** for the most predictable speech-synthesis behavior.

You can also serve it locally if you prefer:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Controls

| Test | Control | Action |
| --- | --- | --- |
| Reaction | `M` | Match |
| Reaction | `Z` | No Match |
| Multitasking | Mouse | Select duplicate numbers / answers |
| Multitasking | Phonebook | Open reference table |
| Multitasking | Agenda | Open schedule |

## Scoring

The app reports **practice metrics**, not official All Options or TradingInterview.com scores.

For Reaction, a correct response adds one point; incorrect and skipped responses do not. Accuracy and average response time are reported separately.

For Multitasking, the local scoring rewards correct duplicate selections and fully correct rows, penalizes incorrect selections, and gives larger rewards to accurately timed answers. It is intended to make speed/accuracy trade-offs visible rather than reproduce a proprietary scoring algorithm.

## Training suggestions

For Reaction, first aim for high accuracy and let speed improve naturally. Rotation is part of the identity, so do not mentally rotate a figure into a match.

For Multitasking, avoid finishing one task completely before attending to the other. Keep scanning numbers while retaining the audio instruction, use the lookup tables quickly, and periodically check the timer when a timed instruction is active.

## Technical notes

The entire trainer is intentionally contained in one static `index.html` file:

- Vanilla HTML/CSS/JavaScript
- SVG-generated visual stimuli
- `SpeechSynthesisUtterance` for audio questions
- No analytics or network requests
- No user data collection

## Disclaimer

This is an unofficial educational practice project. Assessment formats can change, and this trainer should not be treated as a representation of the exact live assessment or its scoring.