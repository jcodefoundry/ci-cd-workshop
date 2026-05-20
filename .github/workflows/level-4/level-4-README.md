# Level 4 — Toad's Treasure House

Doel (verhaal): Verzamel Toad's schatten: bouw een artifact en leg 'm veilig weg.

Wat je leert:
- Een build artifact (JAR) produceren met Gradle
- Het artifact uploaden als GitHub Actions artifact

Opdracht:
1. Open `.github/workflows/level-4.yml`.
2. Zorg dat `./gradlew build` een JAR produceert in `build/libs/`.
3. Upload de JAR als artifact met `actions/upload-artifact@v4`.
4. (Optioneel) Voeg `needs: [test]` toe vanuit level 2 zodat upload pas gebeurt na succesvolle tests.

Acceptatiecriteria:
- De run bevat een downloadbaar artifact met de JAR.

Hints:
- Spring Boot maakt doorgaans een fat JAR aan: `build/libs/<project>-<version>.jar`.
- Je kunt ook meerdere bestanden uploaden met een glob, bijv. `build/libs/*.jar`.

Stretch goals:
- Publiceer het artifact naar GitHub Packages (Maven) met Gradle's `maven-publish` plugin.
- Geef de artifactnaam een duidelijke tag (commit SHA, version, datum).
