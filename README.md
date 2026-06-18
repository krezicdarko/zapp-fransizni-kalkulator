# Zapp franšizni kalkulator

Interaktivni financijski „what-if" kalkulator za procjenu Zapp franšize (BiH, KM/BAM).
Samostalna HTML aplikacija — vanilla JS, bez biblioteka, bez build koraka.

**▶️ Live:** https://krezicdarko.github.io/zapp-fransizni-kalkulator/

## Razvoj
- Single-file app; `index.html` se servira preko **GitHub Pages** s grane `main`.
- `index.html` i `zapp-fransizni-kalkulator.html` moraju biti **identični** (detalji u [`CLAUDE.md`](CLAUDE.md)).
- **Deploy = push na `main`** (Pages se osvježi za ~1 min).
- Kloniraj u **običan lokalni folder** (NE u Google Drive / OneDrive) — vidi [`CLAUDE.md`](CLAUDE.md).

## Nastavak rada na drugom računaru
```bash
git clone https://github.com/krezicdarko/zapp-fransizni-kalkulator.git C:\Users\<ime>\projects\zapp-fransizni-kalkulator
cd C:\Users\<ime>\projects\zapp-fransizni-kalkulator
# na početku: git pull --ff-only   ·   na kraju: git add -A && git commit -m "..." && git push
```
