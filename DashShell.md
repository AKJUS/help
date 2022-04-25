# Debian Almquist Shell (Dash)

While Bash is very popular (and so is its syntax), Dash replaced Bash as non-interactive shell in 2011 with the release of Debian 6 (Squeeze). Dash is POSIX-compliant, small and fast. For the interactive shell Bash is still used – which is absolutely fine.

However, Bash is not POSIX-compliant which can be a portability problem, especially when shared with the open-source community. Instead of memorizing different syntaxes and features between different shells – which can be dangerously confusing – I decided to use exactly **one** shell. Since Dash is POSIX-compliant, the choice was clear and I stopped writing shell scripts in Bash.

## Cheat Sheet
### Quoted Variables

In the most cases, you want to place double-quotes (`$VAR`) around variables. This also applies to command substitution. Otherwise not all of the content of the variable – including whitespace – is passed, but the variable gets splitted.

#### Correct

```
RETURN_CODE="$(dpkg-query -s "$PACKAGE_NAME" >/dev/null 2>&1)"
```

#### Wrong

```
RETURN_CODE=$(dpkg-query -s "$PACKAGE_NAME" >/dev/null 2>&1)
```

```
RETURN_CODE=$(dpkg-query -s $PACKAGE_NAME >/dev/null 2>&1)
```

### Command Substitution

#### Deprecated

Backticks (`` ` ``) – or also called backquotes – are deprecated for command substitution. Instead use `$(...)`.
```
RETURN_CODE="`dpkg-query -s "$PACKAGE_NAME" >/dev/null 2>&1`"
```



