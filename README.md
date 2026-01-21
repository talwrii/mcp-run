# mcp-run
An mcp wrapper which just **runs** a commnd. No configuration files. 

This is unreviewed AI-generated code.

## Motivation
I don't really want to write mcp servers. Well sometimes I do - but often I just want to run things.
In this case MCP is really just a CLI command with a a little documentation. `mcp-run` adds the documentation and runs the command.

You don't need to create yaml files for this. It is a single command that you can put in your conig.

## Alternatives
mcp proxy (mcptools) — env vars only, not real args
mcp-this — YAML files
MCPShell — YAML files

## Installation
`pipx install mcp-run`

## Usage
```
mcp-run <command> <description> [options]
```
* `--pos-arg "name description"` positional argument
* `--flag "-f= description"` flag with value
* `--flag "-f description" booelan flag

Wire this into your LLM. For claude this looks like:

```
"mcpServers": {
    "convert": {
      "type": "stdio",
      "command": "mcp-run",
      "args": [
        "convert",
        "Convert and resize images",
        "--pos-arg", "input Input file",
        "--pos-arg", "output Output file",
        "--flag", "-resize= Resize dimensions",
        "--flag", "-quality= JPEG quality",
        "--flag", "-verbose Verbose output"
      ]
    },
```

## About me
I am @readwithai. I am enjoying merging my consciousness with an AI to be as a demigod. If you feel the same you might like to follow me on github https://github.com/talwrii where I will push as stream of useful tools that give you AI-mediate power
