# MakerWorks Unraid Templates

Unraid Community Applications templates for the MakerWorks suite.

## Templates

- `makerworks-postgres.xml` - PostgreSQL 15 database used by MakerWorks and optional shared StockWorks storage.
- `makerworks-v2.xml` - MakerWorks storefront, quoting, checkout, and admin operations.
- `stockworks.xml` - StockWorks inventory, material, merch, and incoming job visibility.
- `printlab.xml` - PrintLab printer dashboard, Bambu integration, and Works service bridge.

## Unraid Notes

Create the shared Docker network before installing the suite templates:

```bash
docker network create makerworks-net
```

Install `makerworks-postgres` first, then use PostgreSQL connection strings that point at `makerworks-postgres` from the other containers on the shared network.

Example MakerWorks database URL:

```text
postgresql://postgres:change-this-password@makerworks-postgres:5432/makerworks?schema=public
```

Do not leave template placeholder passwords or secrets in production. Generate long random values for every masked field before starting the containers.

## Community Applications

These XML files are intended to live in the `main` branch so Community Applications can index the repository. Before submitting to CA, create the required Unraid forum support thread and replace the `<Support>` values if the CA moderators require a forum URL instead of GitHub issues.
