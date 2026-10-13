# sync

> [!NOTE]
> Infra branch for this fork. The archive lives on
> [master](https://github.com/xero/sixteencolors-archive/tree/master).

---

## How it works

This orphan branch is the fork's default branch and holds only the sync
workflow. Scheduled workflows run from the default branch, so parking the
workflow here keeps `master` a true mirror of
[sixteencolors/sixteencolors-archive](https://github.com/sixteencolors/sixteencolors-archive)
with zero divergence.

[sync-fork.yml](./.github/workflows/sync-fork.yml) runs daily and calls the
GitHub `merge-upstream` API to fast-forward `master`. No checkout, no PAT,
no third-party actions. If `master` ever diverges, the fast-forward fails
loudly instead of force-pushing over local commits; fix it with a manual
force-push back to the upstream SHA.
