# agent-skills-mirror (**For personal use**)

Public mirror of the handful of local agent skills that have **no usable public upstream**,
published so **CC Switch** can track them as repository-backed skills and update them online
(its updater only reads `https://github.com/<owner>/<repo>/archive/refs/heads/<branch>.zip`).

Scope: **18 skills** — the ones that are self-authored / private / only exist as third-party
reposts / whose real upstream removed them or ships an archive above CC Switch's 128 MB limit.
Everything else in the library is tracked against its real upstream repository instead.

Layout: one directory per skill, each containing `SKILL.md` plus its resources.

Content is byte-identical to the local copies under `~/.cc-switch/skills/<dir>` at mirror time,
so CC Switch's directory hash (SHA-256 over sorted `relpath\0content\0` pairs, dot-prefixed
files ignored) matches and no spurious "update available" appears.

Keep the directory payload under 128 MB: CC Switch aborts any repo whose archive extracts past
that limit, and then all skills of that repo are skipped during update checks.

> `.gitattributes` disables text/EOL normalization on purpose: any rewrite would change the
> hash and make CC Switch report a fake update.
