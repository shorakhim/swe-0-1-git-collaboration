# Git Collaboration

This assignment is about git, not Python. The interesting part is the workflow: how to

- Fork a repository
- `git clone` a remote repository
- `git add` to stage and `git commit` to commit changes
- `git push` committed changes from a local repo to a remote repo
- `git pull` changes from a remote repo to a local repo
- Handle merge conflicts

Along the way, you will create merge conflicts on purpose. They are a great
place to learn the foundations of working together in git, and it's better to
meet your first one now than during a real deadline.

Finally, you will write a reflection together on using `git`.

**Table of Contents**:

- [Setup](#setup)
- [AI Use on This Assignment](#ai-use-on-this-assignment)
- [Requirements](#requirements)
- [Reflection Questions](#reflection-questions)
- [Instructions](#instructions)
- [Troubleshooting Tips](#troubleshooting-tips)
- [Bonus](#bonus)


## Setup

This is a team assignment. Decide now who will be **Partner A** and who will be **Partner B** and stick to those roles for this assignment.

1. **Partner A** forks this repository. Only one of you forks it. Partner B
   does not fork anything.

   ![Click the fork button and select your account to make your copy of the repository](how-to-fork.png)


3. In the **forked** repository, Partner A adds Partner B as a collaborator so
   both of you can push to it.
   [Here is how you do that](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository).
   Partner A shares the repo URL, and Partner B accepts the invitation on
   GitHub. Check your email if you don't see a button pop up to accept the
   invitation.
4. **Both partners** `git clone` the forked repo onto your own computers into
   `development/mod-0` using SSH.
5. **Both partners** check that VS Code can be opened from the terminal:

   ```sh
   code --version
   ```

   If you see a version number, move on. If you see `command not found`, open
   VS Code, open the Command Palette (`Cmd+Shift+P` on Mac, `Ctrl+Shift+P` on
   Windows), run **Shell Command: Install 'code' command in PATH**, then close
   and reopen your terminal and try again.
6. **Both partners** run these two commands once. The first makes `git pull`
   behave the way these instructions expect. The second makes git open VS Code
   instead of Vim when it needs you to write a message.

   ```sh
   git config --global pull.rebase false
   git config --global core.editor "code --wait"
   ```

## AI Use on This Assignment

Use whichever mode matches where you are with this material. Both are fine,
and most people move between them as a concept clicks.

**Tutor mode.** The AI explains, questions, quizzes, and critiques, and you
write every line you submit. For this assignment that means asking it what a
merge conflict actually is, or what `git pull` does that `git clone` does not.
Ask it a hundred questions — that is the whole point. What you do not do is
ask it to write your commands, your story, or your reflection. Paste this at
the start of a chat and it will hold for the rest of the conversation:

> You are acting as a tutor. Your job is to explain what this coding question
> is asking, clarify confusing wording, and highlight the relevant concepts I
> need to know — but do not provide the full solution or code that directly
> answers the question. Instead, rephrase the problem in simpler terms,
> identify what is being tested, and suggest what steps or thought processes
> might help. Ask me guiding questions to make sure I am thinking critically.
> Do not write the final function, algorithm, or code implementation.

**Implementer mode.** You write a specification first, the AI writes code from
it, and then you verify that code line by line. For this assignment, hold off.
Typing these `print()` statements and git commands out by hand is what makes
the git workflow stick, and there is very little to specify.

You own every line either way, and you will be asked to explain it.

## Requirements

You will work in pairs to write Python `print()` statements to tell a story!
You can tell any story that you want (keep it appropriate for school/the
workplace). Along the way, you will create and resolve merge conflicts on
purpose. You will then write one reflection together on using `git`. See below
for the questions.

**Requirement 1:** Your commit history shows two merge commits resolving conflicts, one made by each partner.

**Requirement 2:** Your `main.py` file has at least 10 separate `print()` statements.

**Requirement 3:** During Part 3, your commit history shows you and your partner alternated pushing commits.

**Requirement 4:** Your `REFLECTIONS.md` file includes answers to all of the questions below. **You only need one copy of this file**, written together (see Part 4).

## Reflection Questions

Answer each in 2–5 sentences. Specifics from your own session (exact commands,
error messages, commit messages) count for more than general definitions.

1. **Where does your code live?** Describe (or sketch and include an image of)
   where your changes exist after each step: after you save the file, after
   `git add`, after `git commit`, after `git push`, and after your partner runs
   `git pull`. At which point can your partner see your work?

2. **Your predictions vs. reality.** In Round 1, step 5, you each predicted
   what would happen when Partner B pushed. What did each of you predict, and
   what actually happened? Using what you know now, explain *why* git rejected
   the push. Then explain what `git pull` did that the push couldn't.

3. **Resolving a conflict.** Pick one of the two conflicts you resolved
   (Round 1 or Round 2). How did you and your partner decide what to keep?
   How did you confirm the resolution was correct before pushing?

4. **Getting unstuck.** Describe one moment when something didn't work or
   didn't match what you expected, in the warm-up or while writing the story.
   What was the exact message or result? What did you check first (for
   example `git status` or `git remote -v`), and what fixed it?

5. **Commit messages for a team.** Look at your commit history on GitHub. Pick
   the most useful commit message and the least useful one, and rewrite the
   weak one here (you don't need to change the message on GitHub). Then
   explain: if five people were working in this repo instead of two, why would
   clear commit messages and pulling before you start matter even more?

## Instructions

Read all of these before you start. There are four parts:

1. **Setup:** get both partners connected to the same repo
2. **Warm-up:** do one clean push/pull, then cause and fix a merge conflict on purpose
3. **Write the story:** alternate `print()` statements until you have at least 10
4. **Reflect:** answer the reflection questions together in one file

### Part 1: Warm-up

#### Round 0: A clean push and pull

This round checks that your setup works before anything tricky happens.

1. **Partner A** adds this line to the top of `main.py`, with your real names:

   ```python
   print("Written by: Partner A and Partner B")
   ```

2. **Partner A** stages, commits, and pushes:

   ```sh
   git add -A
   git commit -m "add authors"
   git push
   ```

3. **Both partners** check the repo on GitHub and confirm the commit is there.
4. **Partner B** runs `git pull`, opens `main.py`, and confirms the line
   appeared.

If any step failed, stop and use the [Troubleshooting Tips](#troubleshooting-tips)
before moving on. Don't start Round 1 until Round 0 works.

#### Round 1: Your first merge conflict (Partner B resolves)

A merge conflict happens when two people change the **same line** and git
can't decide whose version wins, so it asks you. You're going to cause one on
purpose, so you'll know what to do when one happens by accident later.

1. **Both partners** run `git pull`, then `git log --oneline -1`. Confirm you
   both see the same commit.
2. **Both partners** add this line below the authors line, and each of you
   fills in a title for your story **without telling your partner**. Your
   titles must be different, or git won't see a conflict.

   ```python
   print("Title: ")
   ```

3. **Both partners** stage and commit:

   ```sh
   git add -A
   git commit -m "add title"
   ```

4. **Partner A** pushes. It should succeed.
5. **Before Partner B pushes, predict:** what do you think will happen? Each of
   you writes down your prediction on your phone or on a piece of paper, not
   in the repo. Don't share them yet!
6. **Partner B** pushes. It will be rejected. Read the message out loud
   together. What is git telling you to do?
7. **Partner B** runs `git pull`. Git will report a conflict. Run `git status`
   and read what it says about `main.py`.
8. **Partner B** opens `main.py` and finds something like this:

   ```text
   <<<<<<< HEAD
   print("Title: Partner B's title")
   =======
   print("Title: Partner A's title")
   >>>>>>> a1b2c3d...
   ```

   The top section (`HEAD`) is **your** version. The bottom section is the
   version that came from GitHub. Decide together on one title: pick one, or
   combine them.
9. Edit the lines so only the final version you agreed on remains, and delete
   all three marker lines. Edit by hand. Don't use VS Code's "Accept Current /
   Accept Incoming" buttons this time, so you can see exactly what git is
   asking for.
10. Run `python3 main.py`. If you left a marker in, it will crash, and that's
    how you check your work.
11. **Partner B** stages, commits, and pushes the resolution:

    ```sh
    git add -A
    git commit -m "resolve merge conflict in title"
    git push
    ```

12. **Partner A** runs `git pull` and confirms the agreed-on title arrived.

#### Round 2: Swap roles (Partner A resolves)

Repeat Round 1 with these changes:

- Add `print("Setting: ")` below the title line instead.
- Use `"add setting"` and `"resolve merge conflict in setting"` as your commit messages.
- **Partner B** pushes first (step 4).
- **Partner A's** push is rejected, and **Partner A** pulls, resolves, and pushes (steps 6–11).
- **Partner B** pulls to confirm (step 12).

#### If you get lost

`git merge --abort` undoes the pull and puts your files back to how they were
before it. Your commit is still there. Run `git pull` again (step 7) and
resolve the conflict from there. Nothing is broken.

### Part 2: Write the story

The three lines from the warm-up are the start of your story and count toward
your 10 `print()` statements.

1. Whoever resolved the last conflict (Partner A) drives first. The driver
   runs `git pull`, then **types out** the next `print()` in `main.py` while
   the other partner reviews. Then:
   - stage: `git add -A`
   - commit: `git commit -m "description of the change"`
   - push: `git push`
2. Check the repo on GitHub to confirm the commit arrived.
3. Swap. The new driver runs `git pull` to get that commit, types out the
   next `print()`, and pushes.
4. Keep swapping for *every* `print()` statement until you have at least 10
   statements. **Every push means your partner pulls before they start.**
5. If you hit a merge conflict by accident, good. You already know what to do.
   Resolve it the same way you did in the warm-up.

Your commit history should alternate between you.

Run your code at any point with:

```sh
python3 main.py
```

### Part 3: Reflect

You write **one** `REFLECTIONS.md` together. Working on one computer keeps the
two of you from creating conflicts in this file.

1. **Both partners** run `git pull` so you're working from the latest version.
2. Sit together at **one** computer. Open `REFLECTIONS.md` (create it in the
   root of the repo if it doesn't exist) and answer the
   [Reflection Questions](#reflection-questions). Both partners contribute to
   every answer, and the other partner shouldn't edit the file on their own
   computer while you're writing.
3. Stage, commit, and push from that computer:

   ```sh
   git add -A
   git commit -m "add reflections"
   git push
   ```

4. The other partner runs `git pull` and confirms `REFLECTIONS.md` arrived.

## Troubleshooting Tips

### Did you clone the same repository?

Check which remote you are connected to from inside the git directory:

```sh
git remote -v
```

That prints where you `pull` from and `push` to. Both partners should see the
same two URLs, and both should point at **Partner A's fork**, not at the
Marcy original.

### Seeing `Permission denied (publickey)`?

Your computer's SSH key isn't set up with GitHub. Test it with:

```sh
ssh -T git@github.com
```

If it says `Hi <your-username>!`, SSH works and the problem is somewhere else.
If it says `Permission denied`, your SSH key is missing or hasn't been added to
your GitHub account. Ask an instructor or TA for help setting it up.

### Partner B seeing `Permission to ... denied` or a `403` error?

Partner B hasn't accepted the collaborator invitation yet. Check your email for
the invite from GitHub, or have Partner A resend it from the fork's
**Settings → Collaborators** page. Then try the push again.

### Did you stage, commit, and push?

`git status` tells you. It will say whether you have changes that are not
staged, staged changes that are not committed, and commits that are not
pushed.

### Did you pull your partner's changes?

Run `git pull` before you start typing, every time. Most of the confusion in
this lab comes from skipping it.

### Did you cause a merge conflict?

That's fine. You've already practiced this. Follow Round 1, steps 7–11. If
you get lost partway through, see [If you get lost](#if-you-get-lost).

## Bonus

From here, split the story. Instead of alternating pushes, you
will each work on your own **branch** at the same time. Read about the
[git branching and PR process](https://marcylabschool.gitbook.io/swe/computational-thinking-and-responsible-use-of-ai/mod-0-command-line-interfaces-git-and-github/4-git-branching)
and try it here. You will each create a branch, open a pull request for your
partner to review and merge, and then deal with merging those branches
together. You got this.