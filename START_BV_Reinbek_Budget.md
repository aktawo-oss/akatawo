# Start-Prompt: BV Reinbek, indikatives Kostenbudget (lokal am Mac)

Ausführen: Claude Code im Repo-Root `claude-code-tawo-kalkulation` auf `main` starten, Drive gemountet, `~/.tawo-kalk/gsheet_token.json` vorhanden. Den Block unten 1:1 einfügen. Zwischen den Skills `/clear` und den Block erneut einfügen. `workflow_state.md` zeigt, wo es weitergeht.

---

Projekt BV Reinbek, Neubau Gewerbeobjekt Handel/Lager/Büro, AG Friedrich Duensing GmbH (Ansprechpartner Radim Zbranek), Gewerk Elektro und IT. Abgabe als indikatives Kostenbudget (unverbindliche Kostenschätzung), intern bis 03.12.2026, spätestens 10.12.2026. Ausführung voraussichtlich 2028, Elektro-Bauzeit ca. 26 Wochen.

Arbeite nach CLAUDE.md und den Skills, mit Gates, workflow_state und Abweichungs-Protokoll. Halte die Ausgaben knapp. Die Annahmen unten sind freigegeben, frag dazu nicht nach. STOPP nur bei einer echten Prozess-Abweichung oder einem Script-Fehler nach dem Retry.

**Eingang** (Drive-Ordner `1ZqFfOSkTKKvIRAxImT5eJzHJvziqORY_`):
- `PLAN_LV_BV-Reinbek_bottom-up_2026-11-26.xlsx` (ID `1mLd3NEIAUqNwtgf8-mC9ZCV6HtnKuTzq`): LV-Input im PLAN_LV-Format, OZ 3,3,4, 146 Positionen. Titel 090/091 = Optionen und Bedarf (ohne GP).
- `LV_BV-Reinbek_bottom-up_ohne_Preise_v2_2026-11-26.xlsx` (ID `1OrSRbgtoQd3C-x7ADukKCj1GMZ94sCXm`): Blätter „Zuschläge und Risiken“ und „Mengenbasis“.
- `FRAGENLISTE_LV_BV_Reinbek_beantwortet_2026-11-26.xlsx` und `BEGLEITNOTIZ_BV_Reinbek_v2_2026-11-26.md`: Antworten des AG vom 26.11. und Annahmen. Als Hinweisquelle in `/hinweis-extraktion` verwenden.

**Ablauf**
1. `/projekt-erfassung` Teil A: Zuerst im Register prüfen, ob es für BV Reinbek / Duensing schon eine Nummer gibt. Falls ja, diese verwenden, sonst eine neue ziehen. Drive-Projektordner mit `3_Kalkulation` anlegen, PLAN_LV nach `2_Original LVs/` und als LV-Excel setzen. Teil B schlank: Notion-Eintrag und Steckbrief ja, Quick-Scan kurz.
   - Merkmale: Nutzung `logistik` (das Lager dominiert, Verkauf nur 101 m²). Bauart `neubau`. Leitkennzahl Hallenfläche 2193 m², Quelle: Mengenbasis, Lageplan_EG 0.01 + 0.02 + 0.03 + 0.06. Spur B. oz_structure 3,3,4.
2. `/template-anwendung` mit dem PLAN_LV.
3. `/hinweis-extraktion`.
4. `/vorab-kalkulation`, Spur B, keine Lieferanten-Anfragen.
5. `/kalkulations-analyse`.

**Feste Vorgaben**
- **Mengen nicht ändern:** Sie sind die wahrscheinlichsten Werte ohne Reserve. Das Mengenrisiko geht ausschließlich über die Spannen (Spalte H) in den Risikoaufschlag P80. Kein zusätzlicher Mengenpuffer.
- **Preisstand:** 11/2026. Fortschreibung auf die Mitte der Ausführung 2028.
- **Optionen 090/091:** mit EP bepreisen, ohne GP, getrennt ausweisen, nicht in der Summe Grundangebot.
- **Planungsleistungen:** Planungs-, Dokumentations- und Prüfpositionen (falls im LV vorhanden) als eigene Summe ausweisen.

**Zuschläge (Blatt „Zuschläge und Risiken“). Gesetzte Werte, jeweils als eigene Zeile ausweisen, nicht in die EP verstecken:**

| Zuschlag | Ansatz | Bezug |
|---|---|---|
| Preissteigerung bis 2028 | 8 % | Material und Lohn, gesamtes LV |
| Risiko Reifegrad (keine ELT-Planung, 74 Fragen) | 10 % | EK Grundangebot; deckt Scope- und Technik-Lücken, nicht die Mengen |
| Mengenrisiko | P80 aus den Spannen je Mengenstufe, mit Preisspannen der Engine | alle Positionen; die Differenz P80 minus P50 ist der Aufschlag |
| Erschwernis Montage über 7 m | +20 % Lohn | Pos. 04.0050, 08.0010 und alle Hallenmontagen; Hubarbeitsbühne 26 Wochen als Gerät in der BE |
| Gestaffelte Fertigstellung, Mietereinbau | +4 % Lohn | Grundangebot |
| Bauleitung | 20 h/Woche × 26 Wochen = 520 h BL | gesamtes LV |
| Projektleitung | 4 h/Woche × 26 Wochen = 104 h PL | gesamtes LV |
| Koordination Fremdgewerke und Mieter | in den BL-Stunden enthalten | Titel 07, 15 |
| Netzanschluss und wiederholte IBN | 2 Zusatztermine × 2 Monteure × 8 h | Pos. 03.0010 |
| Lieferzeiten HV und Wechselrichter | keine Reserve, nur Preisvorbehalt im Begleittext | Pos. 03.0010, Option PV |
| AGK, Wagnis und Gewinn | TAWO-Kalkulationsschema der Engine, unverändert | gesamtes LV |
| Sicherheiten | 0,5 % auf die Angebotssumme (Aval Vertragserfüllung und Gewährleistung) | gesamtes LV, Vorbehalt AG 2.3 |

**Doppelzählung vermeiden:** Reifegrad (Scope) und P80 (Menge und Preis) sind getrennte Ursachen. Die Preissteigerung gilt nicht auf die Risikozuschläge.

**Ergebnis am Ende (kurz, Wichtigstes zuerst):**
1. Summen netto, getrennt: Grundangebot (Basis, Zuschläge einzeln, P80), Planungsleistungen, Optionen und Bedarf (EP-Liste). Spanne P50 bis P80 dazu.
2. Top-5-Risiken in EUR.
3. Was vor der Abgabe noch zu entscheiden ist, je Punkt mit Empfehlung. Mindestens:
   - Freigabe der Zuschlagssätze oben
   - Ob P80 oder P50 an den AG geht
   - Vorbehaltstexte: Budget unverbindlich, Preisstand, Lieferzeiten, Sicherheiten offen
   - Verhältnis zum FLB-Engine-Lauf (siehe `UEBERGABE_FLB_Engine.md`): Annahme ist, dass dieses Budget für die Abgabe führt und FLB nur Gegenprobe ist
   - Fach-Pate statt „N. N.“
