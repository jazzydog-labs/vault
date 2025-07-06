# Should Vault Own Secrets?

This document evaluates whether the Vault repository should include secret management or whether secrets should be handled in a separate system.

## Context
Vault currently aims to store schemas, generated code, and project skeletons. Early drafts also included encrypted secrets. Several stakeholders raised concerns about mixing responsibilities.

## Considerations

- **Single Responsibility Principle (SRP)**
  - Keeping secrets together with schemas introduces a broad surface area.
  - A dedicated secrets repository could enforce tighter access and auditing.

- **Encapsulation and Security**
  - Secrets typically require short-lived access and granular permissions.
  - Schemas and code artifacts are mostly public within the organization.
  - Splitting secrets enables different review and rotation policies.

- **Operational Complexity**
  - A combined repo simplifies dependency management but complicates tooling.
  - Separate repos mean extra orchestration when fetching schemas and secrets.

- **Tradeoffs**
  - *In Vault*: simpler setup, but potential for privilege creep and larger blast radius.
  - *Separate Repo*: clearer boundaries and specialized tooling, though more repositories to manage.

## Recommendation
At staff level, the safer approach is to **separate secrets** from Vault. The Vault repo can focus on immutable artifacts like schemas and generated code, while a dedicated secrets service or repository handles encryption, rotation, and audit requirements. Integration points (e.g., secret references in schemas) should be clearly documented.
