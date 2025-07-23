## GraphQL API Repository

Contains GraphQL SDL schemas, changelogs, and some additional content for the Retarus GraphQL API.

---

### Directory Structure Explanation

---

#### /latest/ Directory

**Purpose**  
Contains the `current, released` GraphQL schema and related content.

**Redocly Integration**  
- The `schema/` folder is watched by Redocly for documentation generation and syncing.

**Content**  
- `schema/`: Contains the most up-to-date GraphQL schema in SDL format (`schema.gql`).
- Additional files, if any, relevant to the latest schema.

**Format**  
- Schemas in SDL format (`.gql`).

---

#### /versions/ Directory

**Purpose**  
Archives historical versions of the GraphQL schema and related documentation for reference.

**Format & Content**  
- Each versioned folder (`v1.0/`, `v1.1/`, `v2.0/`, `v2.1/`, etc.) contains:
  - `schema.gql`: GraphQL schema for that version.

**Maintenance**  
- This directory is **not** watched or synced by Redocly.
- Used solely for reference or historical auditing.

---

#### CHANGELOG.md (Repository Root)

**Purpose**  
Single changelog file tracking all GraphQL API changes across versions.

**Location**  
- Stored in the repository root directory, alongside the README file.

**Content**  
- Documents changes, deprecations, and additions for all GraphQL API versions.
- Provides comprehensive change history for developers and maintainers.

---

### GraphQL API Overview

This repository organizes GraphQL schemas by historical versions and the latest release.

1. **Latest GraphQL Schema**  
   - Found in: `latest/schema/schema.gql`
   - Contains the most current API definition for external consumers and documentation portals.

2. **Historical GraphQL Schemas**  
   - Found in: `versions/[version-number]/schema.gql`
   - Each version is preserved with matching documentation to assist in migration or troubleshooting.

3. **Unified Changelog**  
   - Found in: `CHANGELOG.md` (repository root)
   - Single source of truth for all API changes across versions.

---

#### Redocly Integration

- Only the contents in the `/latest/schema` directory are actively monitored and synced by Redocly for generating developer-facing documentation.
- The `/versions/` directory is not watched by Redocly. Historical files are available for download and audit but _not_ for live documentation generation.

---

### Working with This Repository

**Update Workflow**

- The current, official schema (SDL) should be maintained in `latest/schema/`.
- When releasing a new version:
  - Move the previous latest schema and documents into a new `/versions/[version]/` folder.
  - Update `latest/schema/` with the new schema file.
  - Update the `CHANGELOG.md` with version changes.
- Add additional content, if any, to the versioned directory.

---

**Redocly Documentation Builds**

- _Only_ changes to the `latest/schema` directory trigger content updates in Redocly. The updated content is automatically published to the `GraphQL API Reference` section under https://developers.retarus.com/.

---

### Summary Table of Key Directories

| Directory                     | Purpose                                              | Redocly Watched | Contents                                 |
|-------------------------------|-----------------------------------------------------|:---------------:|------------------------------------------|
| `/schema/`                    | Current schema (SDL format) for documentation       |      ✅         | `schema.graphql`                         |
| `/versions/`                  | Historical schemas and documentation                 |      ❌         | `{vX.Y}/schema.graphql`, docs            |
| `/CHANGELOG.md`               | Unified changelog for all API versions              |      ⚠️         | All version changes and updates          |

