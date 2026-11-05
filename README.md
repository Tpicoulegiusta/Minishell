# Minishell

A small UNIX shell written in C, inspired by bash. 42 team project.

![C](https://img.shields.io/badge/C-00599C?logo=c&logoColor=white)
![readline](https://img.shields.io/badge/GNU-readline-555)

## Features

- **Interactive prompt** with command history (GNU readline)
- **Lexer and parser** that handle single and double quotes
- **Environment variables**: `$VAR` expansion
- **Pipes**: `cmd1 | cmd2 | cmd3`
- **Redirections**: `<`, `>`, `>>` and **heredoc** `<<`
- **Builtins**: `echo` (with `-n`), `cd`, `pwd`, `export`, `unset`, `env`, `exit`
- **Command lookup** in `PATH`, run with `fork` + `execve`
- **Signals**: `Ctrl-C` gives a fresh prompt, `Ctrl-\` is ignored as in bash, `Ctrl-D` exits

## How it works

```
input line ──► lexer ──► parser ──► executor
               tokens    commands,   builtins run in the shell,
               quotes    pipes and   other commands forked and
                         redirs      run with execve
```

## Build and run

Requirements: Linux, `make`, `cc` and the readline library.

```bash
sudo apt install libreadline-dev
git clone https://github.com/Tpicoulegiusta/Minishell.git
cd Minishell/sosheil_maison
make
./minishell
```

Example:

```bash
PROMPETEUH% export NAME=42
PROMPETEUH% echo "hello $NAME" | tr a-z A-Z > out.txt
PROMPETEUH% cat << EOF
> heredoc works
> EOF
```

## Team

- **Tommi Picoulet-Giusta** (tpicoule): [ta part du travail]
- [coéquipier] : [sa part du travail]
