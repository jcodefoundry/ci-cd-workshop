# Level 2 — Koopa's Fortress

Doel: Versla de Koopa‑bewakers met je test‑skills.

Wat je leert:
- Tests uitvoeren in CI
- Test rapporten uploaden voor analyse

Opdracht:
1. Open `.github/workflows/level-2.yml`.
2. Vul de TODO's in zodat `./gradlew ...` draait en faalt bij mislukte tests.
3. Upload test rapporten als artifact (bepaal zelf wanneer dit moet gebeuren).

Acceptatiecriteria:
- Een failing test zorgt dat de job faalt.
- Test rapporten zijn te downloaden uit de Actions run (XML + HTML reports).