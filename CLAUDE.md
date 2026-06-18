# Zapp franšizni kalkulator — project context for Claude

Single-file static **HTML** app (vanilla JS, no libraries, no build step) — an interactive
financial "what-if" calculator for evaluating a Zapp franchise (Bosnia; currency KM/BAM; real
Banja Luka data). Autosaves to `localStorage` key `zapp-kalkulator-v2`.

Modes (tabs): O = Pregled, A = Fransizer, C = Top restorani, B = Troškovi restorana,
T = Trošak logistike, V = Vlasnička struktura.

## Repo & live site
- **Repo (public):** https://github.com/krezicdarko/zapp-fransizni-kalkulator — branch `main`.
- **Live (GitHub Pages):** https://krezicdarko.github.io/zapp-fransizni-kalkulator/
  Pages serves `index.html` from the **root of `main`** and reflects the **last pushed commit**
  (live ~1 min after a push).

## ⚠️ Dual-file sync rule (critical)
`index.html` and `zapp-fransizni-kalkulator.html` must stay **byte-for-byte identical**.
Make the **same edits to BOTH** files (don't blindly `cp`-overwrite — they are sometimes
hand-edited). **Before committing, verify they match** (`git diff` / `cmp index.html
zapp-fransizni-kalkulator.html`). Pages uses `index.html`; if the twin drifts, they silently diverge.

## Deploy = push to `main` (default)
Commit + push to `main` is the default for every change (publishing publicly via Pages is accepted).
Use clear commit messages.

## Verify before pushing
- Run a local static server for this folder and open `index.html`; exercise the **mode you changed**.
- Check at **~375px (mobile)** and **~1280px (desktop)** — the app is responsive.
- Prefer DOM inspection over screenshots when verifying.

## Scope
Edit only the mode/page currently assigned; ask before touching other modes unless it is an
explicitly app-wide change.

## Environment / git — IMPORTANT
- **Do NOT keep the working clone inside Google Drive / "Shared drives" / OneDrive.** Background
  sync re-encodes files (CRLF/BOM), creates phantom git diffs, and can corrupt `.git`. Clone into a
  **plain local folder** on each machine (e.g. `C:\Users\<name>\projects\...`) and move work between
  machines via **git pull / git push** only.
- Line endings are pinned to **LF** via `.gitattributes`. If files ever show as fully "modified" for
  no reason, run `git add --renormalize .` once and commit.
- **Two-machine loop:** START `git pull --ff-only` (if refused → `git pull --rebase`, resolve, continue);
  END `git add -A && git commit -m "..." && git push`.

> This file carries context that otherwise lives only in one machine's local `~/.claude` memory,
> which does **not** travel between machines.
