# Level 5 — Bowser's Castle

Doel (verhaal): Bestorm Bowser’s kasteel met een Dockerized applicatie.

Wat je leert:
- Een container image bouwen met Spring Boot buildpacks (`bootBuildImage`)
- Alleen pushen naar een registry (GHCR) vanaf `main`

Opdracht:
1. Open `.github/workflows/level-5.yml`.
2. Stel een image‑naam in, bijv. `ghcr.io/<owner>/<repo>:<sha>`.
3. Log in op GHCR met `docker/login-action@v3` en `GITHUB_TOKEN` (alleen op `main`).
4. Bouw de image met `./gradlew bootBuildImage --imageName <image>`.
5. Push de image alleen als `github.ref == 'refs/heads/main'`.

Acceptatiecriteria:
- De workflow bouwt een image succesvol.
- Push vindt alleen plaats op `main` (controleer de logs; op andere branches mag push niet gebeuren).

Permissies & secrets:
- Voeg aan de workflow `permissions: packages: write` toe om naar GHCR te pushen.
- `GITHUB_TOKEN` is voldoende voor authenticatie naar GHCR binnen dezelfde repo/org.

Hints:
- IMAGE variabelen handig instellen:
  - `IMAGE=ghcr.io/${{ github.repository }}:${{ github.sha }}`
  - Optioneel: ook `latest` tag pushen.
- Actions: `docker/login-action@v3`, `actions/setup-java@v4`, `gradle/actions/setup-gradle@v4`.

Stretch goals:
- Voeg image labels toe (build metadata) via Gradle of `pack` arguments.
- Publiceer een SBOM of vulnerability scan (bijv. Trivy action).
