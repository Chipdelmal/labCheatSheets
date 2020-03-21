# tMux

Start *tmux* session:

```bash
tmux
```
Start *tmux* session with name:

```bash
tmux new -s NAME
```

List active *tmux* sessions:

```bash
tmux ls
```

Attach to active *tmux* session by ID:

```bash
tmux attach -t ID
```

Detach active *tmux* session (keyboard):

```
CTRL + B
then d
```

Kill session:

```bash
tmux kill-session -t NAME
```

Add a new panel to the *tmux* session (keyboard):

```
CTRL + B
then %
```

Cycle through panels layouts (keyboard):

```
CTRL + B
then SPACEBAR
```
