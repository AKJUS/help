# Debian Almquist Shell (Dash)

While Bash is very popular (and so is its syntax), Dash replaced Bash as non-interactive shell in 2011 with the release of Debian 6 (Squeeze). Dash is POSIX-compliant, small and fast. For the interactive shell Bash is still used – which is absolutely fine.

However, Bash is not POSIX-compliant which can be a portability problem, especially when shared with the open-source community. Instead of memorizing different syntaxes and features between different shells – which can be dangerously confusing – I decided to use exactly **one** shell. Since Dash is POSIX-compliant, the choice was clear and I stopped writing shell scripts in Bash.

## Helpful Tips
### 1.0 STDERR and STDOUT

In order to redirect output to STDERR, you can use `>&2` either at the end or at the beginning to improve readabilty:

```shell
>&2 printf '%s\n' "This is an error message."
```

Suppress standard output:

```shell
>/dev/null nft --version
```

Lets assume the command before (`nft ...`) is just used in order to receive the exit code to find out, if the package is installed or not:

```shell
RESULT=$(>/dev/null nft --version)
```

In that case we need to both suppress STDOUT *and* STDERR, because either it will return the version or an error message (`command not found`):

```shell
RESULT=$(>/dev/null 2>&1 nft --version)
```

---

### 1.1 Return does not return boolean

Bear in mind that return does not return a boolean, but an exit code which is a positive integer between 0 and 255. While 0 stands for success, any other value indicates an error:

```shell
# Check if string is an unsigned integer (also +1 is not considered as be valid)
func_IS_UNSIGNED_INTEGER() {
	NUMBER="$1"
	
	case "$NUMBER" in
		*[!0-9]* | '')
			# False
			return 1
		;;
	esac
	
	# True
	return 0
}
```

---

### 1.2 printf *vs* echo

You should use `printf` instead of `echo`, because it is more portable:

#### echo

```shell
echo "Text with a new line after it."
```

#### printf

```shell
printf '%s\n' "Text with a new line after it."
```

<sub>
<b>References</b>
<br>- https://askubuntu.com/questions/467747/which-is-better-printf-or-echo
<br>- https://unix.stackexchange.com/questions/65803/why-is-printf-better-than-echo
</sub>

---

### 1.3 Quoted Variables

In the most cases, you want to place double-quotes (`$VAR`) around variables. This also applies to command substitution. Otherwise not all of the content of the variable – including whitespace – is passed, but the variable gets splitted.

#### Correct

```shell
RESULT="$(dpkg-query -s "$PACKAGE_NAME" >/dev/null 2>&1)"
```

#### Wrong

```shell
RESULT=$(dpkg-query -s "$PACKAGE_NAME" >/dev/null 2>&1)
```

```shell
RESULT=$(dpkg-query -s $PACKAGE_NAME >/dev/null 2>&1)
```

#### Deprecated

Backticks (`` ` ``) – or also called backquotes – are deprecated for command substitution. Instead use `$(...)`.
```shell
RESULT="`dpkg-query -s "$PACKAGE_NAME" >/dev/null 2>&1`"
```

<sub>
<b>References</b>
<br>- https://unix.stackexchange.com/questions/118433/quoting-within-command-substitution-in-bash
</sub>

---

### 1.4 Comments

```shell
# Single line comment
```

```shell
: '''
Comment
over
multiple
lines.
'''
```
