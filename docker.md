# Docker gotchas

## To overcome 'ptrace: Operation not permitted'
Add this to `docker run`: `--cap-add=SYS_PTRACE --security-opt seccomp=unconfined`.

## Use docker logs to look through scrollback (works like `script`)
`docker logs -t [container id] | less` acts like a unix `script(1)`, showing all i/o in a single output.
