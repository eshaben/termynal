# Termynal

A lightweight and modern animated terminal window.
Built for [mkdocs](https://www.mkdocs.org/).

## Installation

<!--termynal: {title: bash, prompt_literal_start: [$]}-->

```
$ pip install termynal
---> 100%
Installed
```

## Usage

Use `<!-- termynal -->` before code block

````
```
// code
```
````

<!-- termynal -->

```
// code
```

### progress

progress, prompt `---> 100%`

````
```
$ show progress
---> 100%
Done!
```
````

<!-- termynal -->

```
$ show progress
---> 100%
Done!
```

### command

command, start with `$`. You can change it with `prompt_literal_start` option.

````
```
$ python
>>> import requests
>>> requests.get('https://exampls.com')
<Response [200]>
>>>
```
````

<!-- termynal -->

```
$ python
>>> import requests
>>> requests.get('https://exampls.com')
<Response [200]>
>>>
```

### multiline command

````
```
> some longish command with \
  many \
    many \
      many \
  arguments
and this is the output
```
````

<!-- termynal -->

```
> some longish command with \
  many \
    many \
      many \
  arguments
and this is the output
```

### comment

comment, start with `#`

````
```
# comment
```
````

<!-- termynal -->

```console
# comment
```

### output

tool's help looks like this:

````
```
$ poetry --help

...
```
````

<!-- termynal -->

```
$ poetry --help

Description:
  Lists commands.

Usage:
  list [options] [--] [<namespace>]

Arguments:
  namespace                  The namespace name

Options:
  -h, --help                 Display help for the given command.
                             When no command is given display help
                             for the list command.
  -q, --quiet                Do not output any message.
  -V, --version              Display this application version.
      --ansi                 Force ANSI output.
      --no-ansi              Disable ANSI output.
  -n, --no-interaction       Do not ask any interactive question.
      --no-plugins           Disables plugins.
      --no-cache             Disables Poetry source caches.
  -C, --directory=DIRECTORY  The working directory for the Poetry
                             command (defaults to the current
                             working directory).
  -v|vv|vvv, --verbose       Increase the verbosity of messages:
                             1 for normal output,
                             2 for more verbose output and
                             3 for debug.

Help:
  The list command lists all commands:

    poetry list

  You can also display the commands for a specific namespace:

    poetry list test

```

## Mkdocs integration

Declare the plugin:

```yaml
...
plugins:
  - termynal
...
```

Optionally, pass options to the processor:

```yaml
[...]
plugins:
  - termynal:
      prompt_literal_start:
        - "$"
        - ">"
[...]
```

This config allows you to use another prompt:

````markdown
```
> command with >
Ok!
```
````

<!-- termynal -->

```
> command with >
Ok!
```

## Credits

Thanks [ines](https://github.com/ines/termynal)
