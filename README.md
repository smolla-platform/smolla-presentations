# smolla-presentations

Presentation ingestion and conversion service handling uploads of PPTX and PDF source files, server-side conversion, slide rasterisation, text extraction, and speaker note capture.

## Repository layout

```
backend/
    src/Smolla.Presentations.Host/   ASP.NET Core web host
    tests/Smolla.Presentations.Tests/ xUnit unit + integration tests
```

## Local development

```
cd backend
dotnet restore
dotnet build
dotnet test
dotnet run --project src/Smolla.Presentations.Host
```

## Workflows

- `ci.yml` — runs on every push and PR
- `deploy-prod.yml` — runs on push to `main`
- `deploy-staging.yml` — runs on push to `develop`
- `deploy-test.yml` — manual dispatch for shared test slot
- `release-please.yml` — opens release PRs based on conventional commits
- `sync-main-to-develop.yml` — back-merges hotfixes from `main` into `develop`

## Versioning

Managed by `release-please`; the canonical version lives in `version.txt` and is propagated to project files on each release.
