---
sidebar_position: 1
---

# Intro

Loggernaut was born out of the countless blog posts and experiences shared by security professionals and developers who uncovered critical insights hidden away in AWS CloudWatch Logs.

While AWS provides the ability to save searches in the console and offers a few examples, many ingenious searches are developed with a specific intent but often fade into obscurity once the desired information is obtained.

Loggernaut empowers you to:

- Preserve your hard-earned searches in a portable YAML format, complete with parameters.
- Easily modify and fine-tune your saved searches by adjusting the parameters.
- Contribute to a collaborative knowledge base at loggernaut.io, where you can share the purpose, context, and rationale behind your searches.
- A location to share the purpose and knowledge behind those searches at [loggernaut.io](https://loggernaut.io)

## Getting Started

Loggernaut is written in [Golang](https://go.dev/) so will work across all operating systems

## What you'll need

- AWS Cli installed
- AWS Cli authenticated to an AWS account

## Installation



## Running Loggernaut

Once you have the above covered check Loggernaut is working as follows:-

```bash
$ loggernaut 

Unlock the secrets buried within log data,
and let Loggernaut be your trusty guide.

Usage:
  loggernaut [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  describe    Describe the searches available
  execute     Execute the CloudWatch Insight search
  help        Help about any command
  list        List available Log Groups

Flags:
      --config string   config file (default is $HOME/.loggernaut.yaml)
  -h, --help            help for loggernaut
  -t, --toggle          Help message for toggle

Use "loggernaut [command] --help" for more information about a command.

```

You can type this command into Command Prompt, Powershell, Terminal, or any other integrated terminal of your code
