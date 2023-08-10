# gptme
README style GPT conversations for any IDE

This script is a command-line utility that works as an interface for the OpenAI GPT-3 and GPT-4 models. The script listens for changes made in markdown files within the `~/gptme/gpt/` directory, and accordingly generates textual content using the GPT-3 or GPT-4 model.

### Usage

Create a .md readme file in your favorite IDE inside `gpt/` dir and start typing and press save to talk to ChatGPT.

```
    Add a hook in your IDE to run a command on save for files in ~/gptme/gpt

    In Sublime Text you can use a package called "Command on Save" and add this to the settings:

    {
      "commands": {
        "/Users/soheil/gptme/gpt/": [
          "/Users/soheil/gptme/run"
        ]
      }
    }

    First character(s) has special meaning:

      4                       Utilize GPT4 if available, GPT3.5 is the default.
      [space] or [new line]   Only send the current prompt in the thread to reduce number of tokens used (cost).
      mm                      Generate image from the prompt. Open '~/gptme/gpt/img.png' to view.

      Custom Instructions
        The following are passed to the "system" role before any conversation.

      =                       System: fix any garammar in the user prompt using excellent English, keep any foul language.
                              This is good for quick and dirty rephrasing of a thought for posting to social media, etc.

      .                       System: give me very short and concise answers and ignore all the niceties that openai programmed you with.
                              Good for avoiding long-winded answers and all the "apologies" and things like "as an AI language model.."

      /                       System: walk through your thinking process step by step.
                              It has been demonstrated that asking it to show its thought process actually improves results.
```

### Main Functionalities
1. Sending file content to GPT-3 or GPT-4 based on the first character(s) in the file.
2. Creating an image from the prompt if the first two characters are 'mm'.
3. Tailoring responses from GPT based on certain prefixes.

Here are the prefixes and their functions:

Prefix | Function
--------|---------
`4` | Use GPT-4 for generating content.
`[space] or [new line]` | Only send the current prompt in the thread to reduce the number of tokens used (cost).
`mm` | Generate image from the prompt.
`=` | Request GPT to fix any grammar in the user prompt using excellent English, but retaining any foul language.
`.` | Ask GPT to provide short and concise answers.
`/` |  Instruct GPT to walk through its thinking process step by step.
 
### How to use
1. Install the utility and set it up in your IDE.
2. Save a markdown file with your content in the `~/gptme/gpt/` directory.
3. Customize the conversation with GPT-3 or GPT-4 by starting your conversation with special prefixes, where the first characters of the conversation have a special meaning.

For API limitations or cost considerations, you may modify the contents of the files to manage the number of tokens used by the models.

The script also allows you to cancel a running task and revert all the changes made by the last command.

Dependencies:
- Python3
- openai
- threading and queue for Python

You need to have the OpenAI API key to use this utility. You can either put your OpenAI API key in an environment variable named `OPENAI_API_KEY` or directly assign it to the `openai_api_key` variable in the script.

Note: The implementation shown above uses an environment variable to assign the API key.

A detailed usage guide can be obtained by running `.<path_to_run_file>/run --usage` in the terminal.
