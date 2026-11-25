# Übergabe: FLB-Engine, BV Reinbek, weiterführen ab S4

Projektordner: `/Users/anabe/FLB-Projekte/projekt-20261124-2125/`
Engine-UI: http://localhost:8774
Konto: **clanabel@tawo.de** (das Konto anabel.kauer@tawo.de ist bis 14:40 Uhr am Limit)

## Stand (25.11., 09:52)

| Schritt | Status |
|---|---|
| S0 bis S3 | fertig |
| H0 | entschieden: **Bid mit Auflagen**, Modus M-LV, Risikoniveau P80, nur Elektro und IT. Der Fach-Pate steht noch auf „N. N.“ |
| S3-Stichprobe | mit den Urteilen der Gegenprüfung abgeschickt, **ob sie angenommen wurde, ist ungeprüft** |
| S4 | lief, **158 von 160 Paketen** fertig |
| S5, S6, H1, S7 bis S9, H2, S11 | offen |
| Fallback | Ein Helfer hat in `nachtlauf_fallback/` ein Elektro-LV aus Baubeschreibung und Plänen erstellt (Mengen und Fundstellen, ohne Preise), dazu die Rahmenbedingungen, die Fragen an den AG und eine interne Liste. **Noch nicht geprüft** |
| H0-Fix | Der Fix für die Kenntnisnahme des Vertragsmanagers liegt nur auf dem Branch `nacht/durchstich-bv-reinbek`. Einen PR gibt es noch nicht |

## Aufträge, in dieser Reihenfolge

1. **Engine prüfen:** Läuft sie auf localhost:8774? Falls nein, neu starten.
2. **S3-Stichprobe:** Prüfen, ob sie angenommen wurde. Falls nein, erneut abgeben.
3. **S4 abschließen:** die letzten 2 von 160 Paketen. Wenn eines hängt, den Fehler nennen und das Paket neu anstoßen.
4. **S5 und S6** durchlaufen lassen.
5. **Bei H1 anhalten:** Das ist ein Tor im UI, das entscheidet Anabel. Bis dahin eine kurze Entscheidungsvorlage schreiben (was liegt vor, welche Risiken, welche Empfehlung).
6. **`nachtlauf_fallback/` parallel prüfen:**
   - Hat jede LV-Position eine Menge, eine Einheit und eine Fundstelle (Dokument und Seite bzw. Plan)?
   - Ist das LV plausibel? (Mengen gegen die Pläne stichprobenartig prüfen, Doppelungen und Lücken bei den Gewerken Elektro und IT suchen)
   - Decken die Fragen an den AG und die interne Liste alle offenen Punkte ab?
   - Ergebnis als `nachtlauf_fallback/PRUEFUNG.md` ablegen.
7. **Nach der Entscheidung bei H1:** S7 bis S9, dann **H2** (wieder ein Tor im UI, das Anabel entscheidet), dann **S11 mit dem Export des PLAN_LV**.
8. **Bei einem Nutzungslimit:** sofort das Konto wechseln, weitermachen und den Stand mit Uhrzeit melden.

## Offen bei Anabel

- [ ] Die Entscheidung bei H0 bestätigen (Bid mit Auflagen, M-LV, P80, Elektro und IT)
- [ ] Den Fach-Paten benennen (statt „N. N.“)
- [ ] H1 und H2 im UI entscheiden
- [ ] Für den H0-Fix auf `nacht/durchstich-bv-reinbek` einen PR anlegen oder den Fix verwerfen

## Regeln

- H1 und H2 **nicht** selbst entscheiden.
- Keine Ergebnisse erfinden oder simulieren. Wenn etwas fehlt, das klar sagen.
- Kurze Statusmeldungen mit Uhrzeit.
