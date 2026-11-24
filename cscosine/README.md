# spdlog: the cscosine fork

spdlog, as built and released by [third_party_base_libs](https://github.com/cscosine/third_party_base_libs) for the
cscosine projects: the upstream release plus a few commits of ours on top. This folder is ours; the rest of the
repository is upstream.

| | |
|---|---|
| Upstream | <https://github.com/gabime/spdlog> |
| Base | upstream tag `v1.17.0` (also in this repository) |
| Our changes | `git log v1.17.0..main` |
| Our releases | tags `v1.17.0-cs.<n>`, see [CHANGELOG.md](CHANGELOG.md) |
| License | upstream's (MIT) |

## Our changes

| Commit | Files | Why |
|---|---|---|
| csCMake presets: the fork built with the csCMake presets on every platform | `CMakePresets.json`, `csCMakeProjectSetup.json` | Built with the csCMake presets: our fmt (`SPDLOG_FMT_EXTERNAL`), PIC, macOS 13.3 |
| cscosine/: where the fork comes from | `cscosine/README.md`, `CHANGELOG.md` | Where the fork comes from, what we change, why |

Upstream's `.github/` stays as it is: GitHub Actions is disabled on this repository.

## Syncing with a new upstream release

Fetch the new upstream tag (`git fetch https://github.com/gabime/spdlog.git refs/tags/<new>:refs/tags/<new>`), rebase our
commits on it (`git rebase --onto <new> v1.17.0 main`), drop those upstream has absorbed, build through
third_party_base_libs, then tag `v<new without v>-cs.1`.
