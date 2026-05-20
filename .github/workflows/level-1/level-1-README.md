
# Level 1 — Yoshi's Island

Doel: Verbind het Mushroom Kingdom met Yoshi's Island.

Wat je leert:
- Een GitHub Actions workflow starten
- De applicatie builden met Gradle

Opdracht:
1. Open `.github/workflows/level-1.yml`.
2. Vervang de TODO's zodat de workflow bouwt met Java 21 en Gradle.
3. Draai de workflow handmatig via het Actions‑tab (workflow_dispatch).
4. (Optioneel) Deze workflow dient nu handmatig afgetrapt te worden. Vervang dit door een echte trigger (`push`).

Acceptatiecriteria:
- Workflow runt succesvol en voert `./gradlew ...` uit.
- Resultaat zichtbaar in GitHub Actions logs.