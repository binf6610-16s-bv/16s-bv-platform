# 16s-bv-platform

BINF6610 final project. A small computing platform with two pipelines:

- **16s-bv**: 16S V3–V4 amplicons of cervical swabs, BV vs no BV (FastQC, cutadapt, vsearch, SILVA 138.2, scikit-bio, MultiQC), in one image, run as one AWS Batch job.
- **variant-call**: the course's germline variant-calling pipeline.

A Dash app with SQLite (`platform/`) registers both pipelines and their versions, submits runs to AWS Batch, keeps the run history and shows each run's results.

## Working agreement
- Every task has a Jira ticket. Work on its own branch; PR title starts with the ticket key (e.g. `BV-12 Add cutadapt stage`).
- A teammate reviews each PR; merge only when CI passes.
- No keys, passwords or AWS account IDs in this repository. CD's key lives only in GitHub secrets.

## Layout (to be filled in)
- `pipeline/`: the 16S pipeline and its Dockerfile
- `variant-call/`: the variant-call pipeline
- `platform/`: the Dash app, the SQLite schema, the register scripts
- `aws/`: job-definition templates
- `.github/workflows/`: CI and CD
