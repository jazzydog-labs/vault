# Project Plan

## 1. Establish Repository
- [x] Create initial repo structure as outlined in `repo_structure.md`.
- [x] WONT_DO Configure CI/CD for automatic version bumps and artifact storage. (skip for now)

## 2. Implement Schema Service
- [x] Decide on storage backend (we will use a database -- postgresql + jsonb).
- [ ] Set up postgresql backend that runs in a docker container with simple key: jsonb schema

## 3. Evaluate Secret Management
- [x] Decide whether secrets belong in Vault or a separate repository (separate repo)
- [x] WONT_DO If kept here, integrate with enterprise KMS for encryption.


## 4. Provide Code Generation Tools
- [ ] Explore language targets (Python, TypeScript, etc.).
- [X] WONT_DO Generate skeletons from schemas and templates (this belongs in foundry/forge)

# push off for later

## 2. Implement Schema Service
- [ ] Build validation pipeline to ensure schemas meet standards.
- [ ] Provide CLI commands for retrieving schema versions.

## 3. Evaluate Secret Management
- [ ] Document integration points and access controls for secret management


## 5. Documentation
- [ ] Write guides describing how to use Vault.
- [ ] Include architecture diagrams and example snippets.
