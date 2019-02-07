# *nix gotshas

## Is shell interactive?
[this](http://tldp.org/LDP/abs/html/intandnonint.html) suggests the following snippet:
```bash
fd=1 # they suggest 0 and stdin, but for practical (output) reasons i'm only interested of stdout
if [[ -t '$fd" || -p /dev/stdout ]]
then
  # interactive
else
  # non-interactive
fi
```
Notes
- `/dev/stdout` points to `/proc/self/fd/1`, and `/proc/self` points to `/proc/<my pid>`.
- `PS1` and `-i` checks work from the shell itself, but not from invoked scripts, hence fd checks.
