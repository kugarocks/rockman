# tmux

Terminal Multiplexer

---

## Sessions

* `tmux ls`: List sessions
* `tmux attach`: Attach to previous session
* `tmux attach -t 0`: Attach to specific session
* `Ctrl + b` + `d`: Detach session
* `Ctrl + b` + `s`: Select session
* `Ctrl + b` + `$`: Rename session
* `Ctrl + b` + `(`: Prev session
* `Ctrl + b` + `)`: Next session

## Windows

* `Ctrl + b` + `c`: Create window
* `Ctrl + b` + `,`: Rename window
* `Ctrl + b` + `n`: Next window
* `Ctrl + b` + `p`: Prev window
* `Ctrl + b` + `&`: Kill window
* `Ctrl + b` + `'`: Switch to window by name/index
* `Ctrl + b` + `0..9`: Switch to window by number

## Panes

* `Ctrl + b` + `"`: Split horizontally
* `Ctrl + b` + `%`: Split vertically
* `Ctrl + b` + `q`: Show pane numbers
* `Ctrl + b` + `o`: Next pane
* `Ctrl + b` + `;`: Prev pane
* `Ctrl + b` + `x`: Kill pane
* `Ctrl + b` + `arrow`: Move to pane
* `Ctrl + b` + `space`: Swap pane
