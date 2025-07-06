# Proposed Repository Layout

Option A – **Monolithic**
```
/ (project root)
│
├── schemas/          # JSON/YAML schema definitions
├── codegen/          # Generated libraries and utilities
├── skeletons/        # Starter project templates
├── secrets/          # Encrypted secrets and API keys
├── docs/             # Design docs and usage guides
└── tools/            # Helper scripts for management
```
Includes everything in one place but mixes concerns.

Option B – **Split Secrets**
```
/ (project root)
│
├── schemas/
├── codegen/
├── skeletons/
├── docs/
└── tools/
```
Secrets would reside in a separate private repository with stricter access.

Option C – **Schema Only**
```
/ (project root)
│
└── schemas/
```
Code generation and secrets become independent services or repositories.
