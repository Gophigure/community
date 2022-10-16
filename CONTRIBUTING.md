# Contribution Guidelines

The [Gophigure Community][community-gophigure] strives to make all past, present, and future
contributors the stars of the show. Software would no *no-ware* without people to write, test
or use it.

And as such, we'd like to...

**Thank you for participating in our community! 🎉**

> **Note**
> This community adheres to our [Code of Conduct](CODE_OF_CONDUCT.md), which is adapted from the
> [Contributor Covenant v2.1][contributor-covenant-v2.1] code of conduct.

## Table of Contents

- [Support](#support)
- [Core Guidelines](#core-guidelines)
    - [Issues](#issues)
        - [Issue Closure](#issue-closure)
        - [Languages](#languages)
    - [Pull Requests](#pull-requests)
    - [Commit Messages](#commit-messages)
        - [Message Examples](#message-examples)
    - [Code Style](#code-style)
        - [Go](#go)
        - [Markdown](#go)
        - [JSON & JSON5](#json--json5)
        - [YAML (YML)](#yaml-yml)
- [Further Reading](#further-reading)

## Support

*"**Help!** I just have a question!" — Unknown Person*

Does this sound like you? Head over to our [GitHub Discussions][community-gophigure-discussions-q-a]
`❓ Questions & Answers` category for help.

> **Note**
> You can also ask questions in the `💬 support` forum channel in our
> [Discord Server][community-gophigure-discord]. It is recommended that you read through the
> `📕 welcome` channel before participating in that community space.
>
> Don't know how to use Discord? Check out their
[support articles](https://support.discord.com/hc/en-us).

## Core Guidelines

This document outlines the core contribution guidelines ("the Contribution Guidelines") that apply
to all repositories and projects under the [Gophigure Community][community-gophigure].

> **Note**
> Some projects might have their own contribution guidelines that are extensions of the ones laid
> forth in this document.

### Issues

The place where issues are created **depends on what the issue is for**, e.g. issues for **glyde**
are to be filed [here](https://github.com/Gophigure/glyde/issues).

#### Issue Closure

Issues pertaining to bug reports may be closed if the bug ...

1. is considered fixed.
2. no longer affects a supported version.
3. is inactive.
4. has no information regarding reproduction or cause.

> **Note**
> If an issue has been closed, feel free to ping a maintainer with reasoning as to why the issue
> should be reopened.

---

#### Languages

While the [Gophigure Community][community-gophigure] is a primarily English-speaking language, we
accept issues **written in any language**.

It is appreciated if a reply with an English translation is created, anybody can post this
translation.

- A quick run through translation software such as
  [Google Translate](https://translate.google.com/) or [DeepL](https://www.deepl.com/translator)
  will suffice.
- Community maintainers are expected to double-check a translation to ensure community safety
  and accuracy, content that violates the [Code of Conduct](CODE_OF_CONDUCT.md) will be dealt with
  in accordance.

---

### Pull Requests

Pull requests are typically used to stage changes to a codebase before committing the changes.

These changes can range from ...
- code,
- dependencies,
- documentations,
- and tools.

#### Setting up your Local Environment

Setting up a local environment to develop on a new codebase can be daunting, especially when there
are a lot of requirements laid out before you.

> **Note**
> Most repositories in the [Gophigure Community][community-gophigure] will have either a
> `REQUIREMENTS` file or have build instructions in the `README` file that outline requirements.

1. Locate and fulfill the requirements for the codebase, these requirements can be found in the
   places named just above.

    These requirements can be things such as ...

    - tools,
    - dependencies,
    - environment variables,
    - and more!

    <br/>

    > **Note**
    > Most, if not **all** projects will require you to use a `git`-compatible tool such as the
    > official `git` executable (available from [this website](https://git-scm.com/)) in order to
    > make changes to the codebase in a way suitable for creating pull requests.

2. [Fork][docs-github-fork] and clone the repository, sometimes dependencies must be acquired
   *after* cloning the repository to your local machine.

    `git clone <uri> [optional path]` *— this will clone the repository at the supplied uri
    (typically a HTTPS or SSH url) to your environment's file system, optionally to a provided path.*

    > **Note**
    > All examples in this document that involve manipulating a `git` repository will assume you are
    > using the official `git` binary as listed above.

    > **Note**
    > Some repositories may use `git` submodules, you can view the documentation on how to interact
    > with them [here](https://git-scm.com/docs/git-submodule).

    Examples of repositories requiring "late" dependency acquisition include repositories built upon
    technologies such as [Node.js](https://nodejs.dev/).

1. Attempt to build or run the project locally, a repository should have steps on how to do this in
   the `README` or `CONTRIBUTING` file.

    If all goes well, you can move onto step 4! Otherwise, you may need to receive
    [troubleshooting support](#support).

2. Create a new branch for your new changes.

    This is done to make syncing upstream changes easier, as opposed to making the process more
    complicated when you choose to modify the base branch.

    `git checkout -b <name>` *— this will create a new branch with the supplied name, based on the
    already checked-out branch.*

    > **Warning**
    > `git checkout` can be a very destructive command if not used with caution! It has the ability
    > to write to both the working and staging areas depending on your action and flags (`-W` and
    > `-S`). It is **highly** recommended that you read the documentation on this command before
    > performing actions not listed here.

3. Make your changes, remembering to abide by the [Commit Messages](#commit-messages) and
   [Code Style](#code-style) sections of this document.

    If you're making a lot of closely-related commits, consider squashing some or all of the commits
    with [`git rebase`](https://git-scm.com/docs/git-rebase).

    > **Note**
    > We *heavily* prefer that the author of the commits performs this action themselves, either on
    > their own volition or by request of a maintainer. This is because squashing and merging
    > through other means, such as when merging a pull request will invalidate commit signatures.

4. `git push [-u origin <name>]` your changes to your fork, then submit a
   [Pull Request][docs-github-pr].

    We expect a very brief explanation of the pull request as the title, and a more in-depth
    description with included reasoning as the body.

---

### Commit Messages

The [Gophigure Community][community-gophigure] uses the
[Conventional Commits][conventional-commits-v1] specification for creating commit messages in its
code repositories.

- Typical messages use the statuses of `feat`, `fix`, `refactor`, or `chore`.
- The scope is the folder path(s) for the source file(s) that was/were edited.
    - **e.g.** `src/folder1/subfolder1` or `src/{folder1,folder2}` where `{` and `}` denote multiple
      sub-folders of `src`. Top-level folders do not need to be denoted with `{` and `}`.
- Messages should be written using the **imperative mood** such as `Make X do Y`.
    - Do not use language such as `Made X do Y` or `Makes X do Y`.
    - Do not use first, second, third etc. perspective writing styles such as `I made X do Y`.
- Treat messages as though they are encoded and read in UTF-8, this means no code-pairs.
- Do not use emojis or otherwise special symbols excluding those found on a **typical QWERTY
  keyboard**. Anyone should be easily able to re-type a message using said keyboard.

#### Message Examples

1. `feat(folder1,folder2): Add new X for Y`
2. `fix(folder1/{subfolder1,subfolder2}): Fix a bug causing X to Y if Z`

---

### Code Style

> **Note**
> This section is strictly global, and other repositories are **very likely** to have extensions to
> this guideline.
>
> This section **will** feature prolific language formats, such as Go or Markdown.

- Files **must** ...
    1. not exceed 100 columns on a line unless it is by a single punctuation mark.
        - Hyphenating words and terms across lines is permitted but not preferred.

            ```
            Pretend that this line would otherwise pass the 100 char-
            acter limit.
            ```

            > ***"What is preferred, then?"** Putting the term or word on the next line.*

            ```
            Pretend that this line would otherwise pass the 100
            character limit.
            ```

    2. end with a new-line.
    3. be encoded in UTF-8 unless they are a binary format or another encoding is required.
    4. use UNIX-style line-endings (LF) unless another is required.
    5. be included using Git-LFS if they are encoded using a binary format.

#### Go

- The formatter to use is [`gofumpt`](https://github.com/mvdan/gofumpt), it is compatible with the
  regular `gofmt` (anything formatted by `gofumpt` will not be altered by `gofmt`).
    - The official Go extension for Visual Studio Code supports `gofumpt`, and there are ways to
      configure IDEs such as JetBrains' GoLand to run `gofumpt` on save for Go source files.
- `import` statements must be formatted in accordance with the `goimports` style.
    - This means that standard library imports appear first and are separated by a new-line from
      others, the imports should also be organized alphabetically within their group.
    - `_` (side-effect) or `.` (namespace) imports are also subject to the same sorting.

    <br/>

    ```go
    package main

    import (
        _ "embed"
        "fmt"
        "os"

        "github.com/Gophigure/glyde/api"
        "github.com/Gophigure/glyde/discord"
        "github.com/Gophigure/glyde/util/httputil"
        "github.com/Gophigure/glyde/util/jsonutil"
    )

    // ...
    ```
- When using an `if ... else` statement to conditionally set the value of a variable, the variable
  should be declared **immediately** before the `if ... else` statement, unless otherwise required
  beforehand or already exists in the current scope.
    - Shadowing a variable also incurs this requirement.

    <br/>

    ```go
    // ...

    /** This code is not necessarily sensical and exists for example purposes. */

    func MyFunction(argument string) string {
        // Declared directly before the if ... else statement.
        var variable1 string
        if argument == "" {
            variable1 = "empty"
        } else {
            variable1 = "non-empty"
        }

        fmt.Println("your string is:", variable1)

        // The argument variable already exists in the scope and does not need to be declared.
        if variable1 == "empty" {
            argument = "default value"
        } else {
            argument += " " + variable1
        }

        return argument
    }

    // ...
    ```

- Otherwise one should follow the official style guides and recommendations available at the
  [Go website](https://go.dev/).

---

#### Markdown

- Headers must follow and precede a an empty line.

    ```md
    This is some content that precedes the header.
    <!-- Imagine this is an empty line. -->
    ### This is a Header
    <!-- Imagine this is an empty line. -->
    This is some content that follows the header.
    ```

- Lists **must** ...
    1. use hyphens (`-`) instead of asterisks (`*`) if unordered.
    2. pad non-list-item children with 1 empty line above and below.
    3. use a `<br/>` tag to force a new line before a non-list-item child if the processor does not
      otherwise insert one and allows this alternate behavior.
    4. align text on a new-line with the text of the first line.

        ```md
        - This text is
          aligned.
        ```

- Bold text must use double-asterisks (`**`) and not double-underscores (`__`).
- URI "variables" must proceed all other content of the document.

    ```md
    ### This is a Header

    This is some content below the header that [references a variable][var1].

    [var1]: README.md
    ```

- Vertical rules ...
    1. may be used to separate sections beginning with a single-pound or three-pound-or-more headers.
      (`#` or `hn` tags if the markdown processor permits the required HTML content).
    2. **must** be written as `---` with no indentation.
    3. **must** follow and precede an empty line.
- Block-quotes **must** ...
    1. follow and precede an empty line.
    2. use a `> ` to begin all new-lines.
- Code-blocks must follow and precede a new line.

---

#### JSON & JSON5

We do not typically use `.json5` files, but if the need arises then the style guide is **the same as
`.json` files** and comments can precede or follow (on the same line) as what they are explaining.

> **Note**
> This style guide for JSON can be ignored if the JSON is intended to be minified.

- Objects **must** ...
    - have their `{` and `}` directly preceding and following (respectively) lines occupied by keys.

        ```json
        { // Keys do not go here.
            "key_one": "value_1"
        } // Keys do not go here.
        ```
    - have each of their keys on a new line.
    - use `snake_case` for keys unless another casing is required.
- Arrays **must** have each of their elements on a new line, unless the **total** length of the
  array is negligible. If any elements are on the line, they must be separated by both a comma and a
  space (`, `).

    > Out of all four of these, **only** the **first and last** are acceptable.

    ```json
    ["this", "is", "fine"]
    ```

    ```json
    ["this", "is", "most", "definitely", "not", "an", "okay", "way", "to", "format", "your", "json", "for", "it", "is", "too", "long"]
    ```

    ```json
    ["this","is","also","not","okay"]
    ```

    ```json
    [
        "this",
        "is",
        "the",
        "preferred",
        "method"
    ]
    ```

---

#### YAML (YML)

- All values intended to be interpreted as strings **must** use quotation marks or other YAML
  features that assert the value is a string, **e.g.** multi-line strings.

    > ***"Why?"** Consistency and the infamous "Norway problem."*

## Further Reading

For further reading, consult project-specific `CONTRIBUTING.md` files.

[docs-github-pr]: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request
[docs-github-fork]: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks

[community-gophigure]: https://github.com/Gophigure
[community-gophigure-discord]: https://discord.com/invite/hpxuuh6uq8
[community-gophigure-discussions]: https://github.com/orgs/Gophigure/discussions
[community-gophigure-discussions-q-a]: https://github.com/orgs/Gophigure/discussions/categories/q-a

[contributor-covenant-v2.1]: https://www.contributor-covenant.org/version/2/1/code_of_conduct.html

[conventional-commits-v1]: https://www.conventionalcommits.org/en/v1.0.0/

[github-community-guidelines]: https://docs.github.com/en/site-policy/github-terms/github-community-guidelines
