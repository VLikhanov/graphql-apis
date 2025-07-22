## GraphQL API Repository

Contains GraphQL SDL schemas, changelogs, and documentation for the Retarus GraphQL API.

---

### Directory Structure Explanation

---

#### /latest/ Directory

**Purpose**  
Contains the _current, active_ GraphQL schema and related content.

**Redocly Integration**  
- The `latest/` folder (and its subfolders) is watched by Redocly for documentation generation and syncing.

**Content**  
- `schema/`: Contains the most up-to-date GraphQL schema in SDL format (`schema.graphql`).
- `additional content/`: Additional files (e.g., `CHANGELOG.md`), if any, relevant to the latest schema.

**Format**  
- Schemas in SDL format (`.graphql`).

---

#### /versions/ Directory

**Purpose**  
Archives historical versions of the GraphQL schema and related documentation for reference.

**Format & Content**  
- Each versioned folder (`v1.0/`, `v1.1/`, `v2.0/`, `v2.1/`, etc.) contains:
  - `schema.graphql`: GraphQL schema for that version.
  - `CHANGELOG.md`: Changelog entries for that version.

**Maintenance**  
- This directory is **not** watched or synced by Redocly.
- Used solely for reference or historical auditing.

---

### GraphQL API Overview

This repository organizes GraphQL schemas by historical versions and the latest release.

1. **Latest GraphQL Schema**  
   - Found in: `latest/schema/schema.graphql`
   - Contains the most current API definition for external consumers and documentation portals.

2. **Historical GraphQL Schemas**  
   - Found in: `versions/[version-number]/schema.graphql`
   - Each version is preserved with matching documentation and changelogs to assist in migration or troubleshooting.

---

#### Redocly Integration

- Only the contents in the `/latest/` directory (and its subfolders) are actively monitored and synced by Redocly for generating developer-facing documentation.
- The `/versions/` directory is not watched by Redocly. Historical files are available for download and audit but _not_ for live documentation generation.

---

### Working with This Repository

**Update Workflow**

- The current, official schema (SDL) should be maintained in `latest/schema/`.
- When releasing a new version:
  - Move the previous latest schema and documents into a new `/versions/[version]/` folder.
  - Update `latest/schema/` with the new schema file.
- Additional release notes or changelogs should be added to the appropriate `CHANGELOG.md` in each versioned directory.

---

**Redocly Documentation Builds**

- _Only_ changes to the `latest/` directory will trigger content updates in Redocly (such as [your developer portal link] or similar documentation hubs).

---

### Summary Table of Key Directories

| Directory                     | Purpose                                              | Redocly Watched | Contents                                 |
|-------------------------------|-----------------------------------------------------|:---------------:|------------------------------------------|
| `/latest/schema/`             | Current schema (SDL format) for documentation       |      ✅         | `schema.graphql`                         |
| `/latest/additional content/` | Additional docs (e.g., changelogs) for latest       |      ✅         | `CHANGELOG.md`, etc.                     |
| `/versions/`                  | Historical schemas, changelogs, documentation       |      ❌         | `{vX.Y}/schema.graphql`, `.json`, docs   |

---

For contributions, need for historical audit, or questions about the schema, please see the individual documentation files found in each version’s directory.
