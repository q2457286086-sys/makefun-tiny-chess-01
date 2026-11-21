# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/q2457286086-sys/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/q2457286086-sys/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 0x88 negamax chess engine in 4 KB of Python. `main.py` is the kit-compressed entrypoint; its readable source is bundled with the submission (too large to ship in the repo under the 8 KB cap).

- Iterative deepening, alpha-beta, transposition table, MVV-LVA + killer move ordering, capture-only quiescence, null-move pruning (R=2), check extensions, and search-level threefold-repetition scoring.
- Fixed 100,000-node budget per move: deterministic, no clock, no randomness, no model calls. Piece-square evaluation (material + PSTs).
- Speaks the env protocol at `MAKEFUN_ENV_URL` (`/game`, `/move`).

Local practice trials (kit env + scorer): src.py trial-0 Elo 1191 (2W 1D 3L), trial-1 Elo 1364 (3W 1D 2L); compressed main.py re-ran trial-0 at Elo 1191, identical to src.py. One compressed trial-2 run scored Elo 876 (opening and colour variance plus two already-lost endgames).

## Run it

```sh
python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=1d9qr14r&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
