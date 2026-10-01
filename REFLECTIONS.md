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

Reflection Questions Response

1. Our code lives on the local computer until I save the file and run the command git add. This adds the file to the staging area which I then commit and add a message to. Git commit puts the change in the local github repository. Then I push the change I made on the local repository into the git cloud repository with the command git push.  My partner then runs the command git pull to see any changes I made. When my partner runs git pull the changes I made are now visible on her local computer.

2. Sho: I predicted that VScode would replace what Zion pushed with what I pushed because I pushed first, or that it would cause an error and both our pushes would fail.
Zion: I predicted that VScode would push both our titles onto the screen.
Git rejected the push because we typed code on the same line and pushed it and the system detected a merging error. It asked use to resolve the error and guided us.

3. For the first error we decided to keep the title Zion picked because the title was more fitting and applied to our social identities more. We confirmed with the command git status to make sure the conflicts were resolved.

4. We got stuck in the beginning setting up the repository in VSCode and both being able to access it. We first tried to resolve it with claude, then asked Loren and Ben for help.

5. Any of the resolve commit messages werer the most useful because we could locate when an issue happened and when we were able to resolve it. If five people were working clear messages would matter even more because it would make everything more confusing and if all of the members commit a message without being clear we would not know what was changed and the other members can overlap the same code and cause a conflict in the repository.