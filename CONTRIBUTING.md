# Contributing to Internal Computing and Calculus for Advanced Statistics Resources

These are recommendations when contributing to the contents of the internal `CCAS` (Computing and Calculus for Advanced Statistics) repository.
They consider contributions to and support code (solutions) and other types of content (Markdown) made via Git.

Note that this is an internal repository, for evaluation items (assignments, exam papers, quizzes) that are to be kept private.
If you plan to contribute to actual public content (lectures, tutorials, demos, assignment statements, assignment skeletons), use the [public (OER) repository](https://github.com/open-education-hub/ccas).

Although meant to be private, these resources adhere to the principles [Open Educational Resources](https://en.wikipedia.org/wiki/Open_educational_resources):
use them, update them, mix them, contribute back.
Aim to keep them private, in order to give students a fair and constructive way to solve assignments, quizzes and challenges without access to solutions / answers beforehand.

## First Steps

Some good first steps and best practices when using Git are explained here:

* the Git Immersion tutorial: <https://gitimmersion.com/>
* the Atlassian tutorial: <https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud>
* this blog post on the `ROSEdu Techblog`: <https://techblog.rosedu.org/git-good-practices.html>

## Language

All of our content is developed in English.
This means we use English for content, support code, commit messages, pull requests, issues, comments, everything.

## Content Writing Style

This section addresses the development of content as Markdown files.

Write each sentence on a new line.
This way, changing one sentence only affects one line in the source code.

Use the **first person plural** when writing documentation.
Use phrases like "we run the command / app", "we look at the source code", "we find the flag".

Use the second person for challenges and other individual activities.
Use phrases like "find the flag", "run this command", "download the tool".

## Images

If images are required, use [draw.io](https://app.diagrams.net/) to create diagrams.
If using external images / diagram, make sure they use a CC BY-SA license and give credits (mention author and / or add link to the image source).

## Issues

When opening an issue, please clearly state the problem.
Make sure it's reproducible.
Add images if required.
Also, if relevant, detail the environment you used (OS, software versions).
Ideally, if the issue is something you could fix, open a pull request with the fix.

## Discussions

Use GitHub discussions for bringing up ideas on content, new chapters, new sections.
Provide support to others asking questions and take part in suggestions brought by others.
Please be civil when taking part in discussions.

## Pull Requests

For pull requests, please follow the [GitHub flow](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork): create a fork of the repository, create your own branch, do commits, push changes to your branch, do a pull request (PR).
The destination branch of pull requests is the default `master` branch.

Make sure each commit corresponds to **one** code / content change only.
If there are multiple commits belonging to a given change, please squash the commits.

Also make sure one pull request covers only **one** topic.

### Commits

Before making a commit, configure your name and email locally using:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Then make sure the email you've just configured corresponds to the one you have [set on GitHub](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/adding-an-email-address-to-your-github-account).

After this, make your changes, `git add` them and then commit them using `git commit -s`.
Always sign your commits using the `-s` / `--signoff` arguments to `git commit`.
This will add the following line at the end of the commit message:

```text
Signed-off-by: Your Name <your.email@example.com>
```

Notice that the details above are the name and email that you configured earlier.

Now the `git commit` command will open your default editor and ask you to write a commit message.
Prefix each commit message title with the chapter it belongs to: `software-stack`, `data`, `compute`, `io`, `app-interact` and the component: `lecture` / `lab`.
An example of a prefix is `compute/lab:`.
Following the prefix, write a short and expressive title on the first line.
Use commit messages with verbs at imperative mood: "Add README", "Update contents", "Introduce feature".

Leave an empty line, then add a relevant description of the changes made in that commit.
This description should include why that change is needed (fixes a bug, improves something that was inefficient, etc.).
Wrap the lines of this description to 75 characters.
How a good commit message should look like: <https://cbea.ms/git-commit/>
Below is an example of a good commit message:

```text
data/lab: Fix Makefile `CFLAGS` error

`CFLAGS` was incorrectly set to optimise the code to the `-O3` level. This
caused the function `vulnerable_func()` to be inlined into the caller
`main()`, making it impossible to overwrite `main()`'s return address with
that of `vulnerable_func()`. This commit fixes the issue by forcing the
compiler to not optimise the code by replacing `-O3` with `-O0` in `CFLAGS`

Signed-off-by: Your Name <your.name@example.com>
```
