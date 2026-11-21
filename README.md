# tiny-chess-01 entry

A 0x88 negamax chess engine in 4 KB of Python. `main.py` is the
kit-compressed entrypoint; its readable source is bundled with the
submission (too large to ship in the repo under the 8 KB cap).

- Iterative deepening, alpha-beta, transposition table, MVV-LVA + killer
  move ordering, capture-only quiescence, null-move pruning (R=2), check
  extensions, and search-level threefold-repetition scoring.
- Fixed 100,000-node budget per move: deterministic, no clock, no
  randomness, no model calls. Piece-square evaluation (material + PSTs).
- Speaks the env protocol at `MAKEFUN_ENV_URL` (`/game`, `/move`).

Local practice trials (kit env + scorer): src.py trial-0 Elo 1191 (2W 1D 3L),
trial-1 Elo 1364 (3W 1D 2L); compressed main.py re-ran trial-0 at Elo 1191,
identical to src.py. One compressed trial-2 run scored Elo 876 (opening and
colour variance plus two already-lost endgames).
