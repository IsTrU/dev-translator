# Dev Translator

You know what you want to change, but you might not know what a developer would call it. Maybe the text feels cramped inside a button, a menu disappears behind another box, or the page looks wrong on your phone. You describe it as best you can, add a screenshot, and hope the coding agent understands.
Dev Translator helps with that conversation. It turns your description into a clear development request, explains the terms that fit your situation, and gives you a prompt to copy into your coding agent. You get a better way to ask for the change and a little vocabulary you can use next time.

## A quick example

You write:

> The words inside the Save button on my profile page are touching the edges. I want more space around the words.

Dev Translator explains that the space inside a button is called **padding**.

It gives you a prompt like this:

```text
Increase the internal padding of the Save button on the profile page.
Give its label more space from the button edges, using the interface's
existing spacing conventions where available.

Check that the full label remains visible and has space on every side.
```

Next time, you can say: “Increase the padding inside the Save button.”

See the [complete English and Arabic examples](EXAMPLES.md) for illustrative responses showing every part of the output.

## What it does

The usual response has four parts:

1. **What you mean:** Your intended result, restated in everyday language.
2. **Useful terms:** A few development terms explained through your own example.
3. **Prompt to copy:** A request that identifies the change and describes how to check that it worked.
4. **Next time, you can say:** A short, natural sentence using what you learned.

It can help with appearance, interactions, bugs, features, and behavior outside the interface. You do not need to use technical language or provide access to your project.

It answers in the language you use, including the explanations and the copyable prompt. English technical terms appear alongside explanations in your language. You can ask for a different prompt language, such as an Arabic explanation with an English prompt.

When a request could mean different changes, it asks a simple question first. For example, “make this smaller” might mean a narrower box, smaller text, or less empty space. It should clarify the result you want without asking you to choose a technical implementation.

## Using screenshots

Attach an image through your coding agent and describe what you want changed. Identify the element by its label, location, or an annotation.

A screenshot can show a problem without proving its cause. Dev Translator should describe what is visible and leave an uncertain cause for the coding agent to investigate. If the generated prompt relies on your image, attach it again when pasting into another conversation.

Image support depends on whether your agent and model can read the attachment. Spoken requests use the transcript supplied by the host app.

## Installation

Dev Translator is a skill made of instructions. It needs no API keys, runtime scripts, or separate service. Your coding agent runs it.

Download the project using **Code → Download ZIP**, or clone it:

```sh
git clone https://github.com/IsTrU/dev-translator.git
cd dev-translator
```

Open a terminal in the project directory containing this README and the `skills` folder. The installation commands below are for macOS and Linux.

### Codex

```sh
mkdir -p "$HOME/.agents/skills"
cp -R ./skills/dev-translator "$HOME/.agents/skills/"
```

The installed file should be `~/.agents/skills/dev-translator/SKILL.md`. See the [Codex skills documentation](https://learn.chatgpt.com/docs/build-skills).

### Claude Code

```sh
mkdir -p "$HOME/.claude/skills"
cp -R ./skills/dev-translator "$HOME/.claude/skills/"
```

The installed file should be `~/.claude/skills/dev-translator/SKILL.md`. See the [Claude Code skills documentation](https://code.claude.com/docs/en/skills).

You can also copy the folder with your file manager. On Windows, follow your agent's guidance for the installation folder in your user profile. Avoid an extra nested `dev-translator` folder. Start a new session if the skill does not appear.

To update, copy the new skill files to the same location. Save any personal edits first. Other agents that support Agent Skills may use the shared `SKILL.md`, following their own installation instructions.

## Use it

In Codex:

```text
$dev-translator The menu disappears behind the box below it. Help me describe the fix and learn the terms.
```

In Claude Code:

```text
/dev-translator The menu disappears behind the box below it. Help me describe the fix and learn the terms.
```

An Arabic request in Codex:

```text
$dev-translator أختار الوضع الليلي وإذا حدثت الصفحة يرجع فاتح. أبيه يتذكر اختياري. اشرح لي بالعربي واكتب البرومبت بالإنجليزي.
```

Explicit invocation is the most predictable way to use it. Automatic selection depends on the agent. Ordinary requests to fix code should stay implementation requests.

The skill prepares your request without changing the project. Review the prompt, then paste it into a coding agent or ask the agent to implement it.

## Feedback

For feedback, include your request, the response, your agent and model, and what you wanted. Misunderstandings, unnecessary questions, and confusing terms are useful examples. Remove private information before sharing screenshots or project details.

## License

[MIT](LICENSE). The installable skill includes its own copy of the license notice.
