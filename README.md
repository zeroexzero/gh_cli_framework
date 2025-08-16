# CLI Framework

This framework contains everything you need to begin writing your own command-line interface program.

## Features

**Param quote-escaping**

```
$ echo -n "Simple ""quoted"" test"
Simple "quoted" test
```

**Command chaining**

```
$ echo -n hello && echo -n world
hello
world

$ echo "Hello world" | grep -o -i hello
Hello
```

**Positional arguments**

```
$ command_name param_0 param_1
```

**Flags**

```
$ command_name -x param_0 -y
```

**Logger**

```lua
log_level = "warning"
logger = Logger.New(log_level)
logger.add_debug("Verbose message")
logger.add_info("Informational message")
logger.add_warning("Warning message") 
logger.add_error("Actionable error message")
logger.add_quiet("Never seen")
```

## Development

### Entrypoint / main

The program "starts" at `./myprogram.src`.

### Commands

Commands are defined in `./Commands/` and are registered in `./myprogram.src`

### Utilities & Helper functions

Included are some helper classes such as

* Ip
* Logger
* Utilities

### Building

This project structure requires you use Greybel unless you want to go insane.

If you're unsure how to build with Greybel, consider reading their [docs](https://marketplace.visualstudio.com/items?itemName=ayecue.greybel-vs)

### Testing

This project utilizes the 0x0Test repository in a submodule.

To run tests, first install all submodules with

```bash
git submodule update --init --recursive
```

Then you may run tests by running the `test.src` file at the root of the project or any `*.test.src` file elsewhere in the project.
