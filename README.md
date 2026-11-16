# aphrody-git

The Git stack as one repository: Git (with the Git for Windows and Microsoft lineages), gh, the
Git for Windows SDK, and the Git libraries for Rust, C, Go and TypeScript, plus gitingest and GitX.
Each one is a fork owned by this repository's owner, checked out as a submodule.

`stack.toml` is the only list. `bun scripts/stack.ts` applies it:

```sh
bun scripts/stack.ts            # forks, .gitmodules, submodules, lineage remotes, status
bun scripts/stack.ts pin        # move every submodule to its fork's branch tip
git submodule update --init windows/git-sdk-64   # the SDK is registered, checked out on demand
```

Submodule URLs are relative (`../<name>.git`), so a fork of this repository uses its own forks.
`STACK_OWNER` overrides the owner read from `origin`.
