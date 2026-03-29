# claude-code-lab

English | [繁體中文](README.zh-TW.md)

`claude-code-lab` is a small example project for testing Claude Code behavior.

The current example focuses on `memory`, using a set of conflicting instructions and config files so you can observe how Claude Code loads memory from different sources.

## What This Example Covers

This repository currently demonstrates:

- how `CLAUDE.md` affects Claude's behavior
- how `.claude/CLAUDE.md` affects Claude's behavior
- how `.claude/rules/*` affects Claude's behavior
- how `setting.json` can mask specific files
- how to inspect which memory sources Claude actually loaded

By comparing Claude's reply language and default programming language, you can infer which instruction source took effect first.

## Usage

1. Copy the example home config into your Claude home directory.

```bash
$ mkdir -p ~/.claude
$ cp -r home.claude/* ~/.claude/
```

2. Enter the `memory` example.

```bash
$ cd memory
```

3. Start Claude Code.

```bash
$ claude
```

4. Try prompts such as:

```text
hi
write a program ...
```

## What To Observe

Check:

- which language Claude uses in its response
- which programming language Claude chooses when your prompt does not specify one

Those outputs help you understand which files were applied.

## Inspect Loaded Memory

Inside Claude Code, run:

```text
/memory
```

This shows which memory-related content Claude has read.

## Masking Files

You can edit the following file to mask specific memory sources:

- `memory/.claude/setting.json`

Use `claudeMdExcludes` to exclude:

- a specific `CLAUDE.md`
- files under `.claude/rules/`
- other memory-related files

After changing the config, run the same prompts again and compare the result.

Note: this repo also includes `settings.local.json` inside the example as an additional comparison case, but it should not be treated as a standard user-side setup file.

## Notes

Traditional Chinese notes:

https://hackmd.io/@56etVO4MQ_OKWoWvbGAV_Q/S1XsEwSibe
