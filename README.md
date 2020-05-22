# fish-todotxt
Simple todo.txt implementation in Fish

## Usage
```bash
Usage: todo [OPERATION]

Help Options:
	-h, --help		Show help options

Operations:
	l, ls, list		Show contents of todo.txt
	e, edit, $EDITOR	Edit contents of todo.txt
	a, add, append		Add task item to todo.txt
	d, del, delete		Delete task item from todo.txt
	s, sort			Sort contents of todo.txt
```

## Installation
### PKGBUILD
`$ makepkg -sic`
### Other
It's just a shell script. Put it in your $PATH and you're good.
