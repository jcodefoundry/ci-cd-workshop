# Level 6 — Rainbow Road

Doel (verhaal): Scheur over Rainbow Road door je pipeline te optimaliseren.

Wat je leert:
- Caching toepassen om builds te versnellen (Gradle wrapper + caches)
- (Optioneel) Concurrency instellen om dubbele runs te annuleren

Opdracht:
1. Open `.github/workflows/level-6.yml`.
2. Vervang de `REPLACE_ME` key‑delen in de cache‑keys door een hash gebaseerd op relevante bestanden, bijv.:
   - `hashFiles('**/gradle/wrapper/gradle-wrapper.properties')` voor de wrapper.
   - `hashFiles('**/*.gradle*', '**/gradle/wrapper/gradle-wrapper.properties', '**/gradle/libs.versions.toml')` voor caches.
3. (Optioneel) Voeg `concurrency` toe zodat nieuwe runs oudere runs op dezelfde branch annuleren.
4. Run de workflow minimaal 2x en vergelijk de buildtijd met en zonder cache hit.

Acceptatiecriteria:
- Tweede (en volgende) runs tonen een cache‑hit in de Actions logs.
- Buildtijd is merkbaar korter bij cache‑hits (indicatief).

Hints:
- Gebruik `actions/cache@v4` met stabiele keys en `restore-keys` prefixes.
- Cache paden:
  - `~/.gradle/wrapper`
  - `~/.gradle/caches`, `~/.gradle/daemon`, `~/.gradle/native`, `~/.gradle/notifications`

Stretch goals:
- Voeg caching toe voor Docker build layers (bij gebruik van Dockerfiles of buildx cache‑to/from).
- Integreer met `gradle/actions/setup-gradle@v4` caching features (dependency cache).
