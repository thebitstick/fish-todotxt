#!/usr/bin/env fish

# fish-todotxt
# Simple todo.txt implementation without projects or contexts

set basename (basename (status -f))
set todo_location $HOME/.todo
set todo_txt todo.txt
set todo $todo_location/$todo_txt
set PAGER less

function usage
	echo "Usage: $basename [OPERATION]"
	echo ""
	echo "Help Options:"
	echo "	-h, --help		Show help options"
	echo ""
	echo "Operations:"
	echo "	l, ls, list		Show contents of todo.txt"
	echo "	e, edit, \$EDITOR	Edit contents of todo.txt"
	echo "	a, add			Add task item to todo.txt"
	exit 0
end

if test "$XDG_CONFIG_HOME" = ""
	set config "$HOME/.config/todo"
else
	set config "$XDG_CONFIG_HOME/todo"
end

set config_file $config/config

if ! test -d $config
	mkdir -p $config
	echo "$basename: configuration directory does not exist. creating $config"
end

if ! test -f $config_file
	touch $config_file
	echo "set todo_location $HOME/.todo" >> $config_file
	echo "set todo_txt todo.txt" >> $config_file
	echo "set PAGER less" >> $config_file
	echo "$basename: configuration file does not exist. creating $config_file with defaults"
end

source $config_file
set todo $todo_location/$todo_txt

for item in $argv
	switch $item
		case "l" "ls" "list"
			$PAGER "$todo"
			exit 0
		case "e" "edit" "$EDITOR"
			$EDITOR "$todo"
			$PAGER "$todo"
			exit 0
		case "a" "add"
			if test -z $argv[2]
				echo "$basename: task not inputted"
				exit 1
			end
			echo $argv[2..(count $argv)] >> $todo
			$PAGER "$todo"
			exit 0
		case "-h" "--help"
			usage
			help 0
	end
end

usage
