# Fetch, pull, and push: What are the differences?
The content below provides insight to help you distinguish the **fetch**, **pull**, and **push** commands. It is important to note that *local repository* refers to the files on your local machine (only accessible to you), and *remote repository* refers to the files in the environment (a collaborative space, such as GitHub, accessible to approved team members). Branches are versions of the code or documentation, which usually contain many files. The primary branch is *master*, which is more appropriately referred to as *main*. With rare exception, when you create a branch to add new or updated code or documentation, you first retrieve this information from the *main* branch to ensure you have the most current files.

| Command | Definition |
| ----------- | ---------- |
| git fetch | This command retrieves changes to remote branches and displays them on your local machine. While you can review these changes, this command does not impact files on your local machine. If you and a team member are updating the same file and the team member creates a PR for your review, you can review changes to the branch by using this command; however, in this case, you will need to resolve merge conflicts. |
| git pull | This command retrieves files from the remote repository, moving them into your local repository and ensuring you have all updates available at this time. This is a critical step, as it can help prevent merge conflicts.|
| git push | This command moves the file(s) updated in your local repository to the remote environment, such as GitHub. If you do not execute this command, updated files remain on your local machine. |

*Examples* best distinguish fetch, pull, and push. While the examples below include VS Code-specific actions, the focus and explanations are relative to fetch, pull, and push. For emphasis, the examples reiterate the command definitions. The examples involve changes to documentation files and assume there are no merge conflicts.

**EXAMPLE #1** assumes you have cloned the Pets repository such that the files on your local machine align with the same files in the remote GitHub environment; in addition, this example assumes you are updating files using markdown (.md) in VS Code. This example lists the steps you must perform to update puppy.md, using fetch, pull, and push. These examples enable you to glean a more reasonable understanding of each command.

**EXAMPLE #1** <br>
**From VS Code . . .**
1.  From the Pets repository in VS Code (local repository), perform a **Fetch** to retrieve and review branches or changes. This command allows you to review updates to the remote branches in this repository. While you can review changes, this action does not impact the files in your local repository.
2.  From the Pets repository in VS Code (local repository), access the main branch (remote repository).
3.  To ensure the main branch has the most current documentation files, click **Pull**. This command retrieves files from the remote repository, moving them into your local repository and ensuring you have all updates available at this time.
4.  From this main branch in your local repository, create a new branch – naming this branch per your internal naming standards. At this point, the new branch is identical to the main branch.
5.  Identify the puppy.md file and make changes before saving your content. 
6.  Stage your changes, add a Commit statement, and click Commit. These actions finalize the saved changes to puppy.md in your local repository. 
7.  To move these changes to the remote repository (GitHub), click **Push**. This command moves the file updated in your local repository to the remote GitHub environment.
8.  From GitHub, create a pull request (PR) specific to your branch. The PR allows team members to review changes to puppy.md and, if all updates are approved, you can merge the PR into the main branch. The main branch now includes your puppy.md updates.
9.  Delete your branch.<br>

**EXAMPLE #2** assumes you have cloned the Pets repository such that the files on your local machine align with the same files in GitHub; in addition, this example assumes you are updating files using markdown (.md) in VS Code. This example lists the steps from the Git Bash command line that you must perform to update puppy.md, using fetch, pull, and push.

**EXAMPLE #2** <br>
**From Git Bash . . .**
1.  cd repo-name
2.  git **fetch** (This command allows you to review updates to the remote branches in this repository. While you can review changes, this action does not impact the files in your local repository.) 
3.  git checkout main
4.  git **pull** (This command retrieves files from the *main* remote repository, moving them into your local repository and ensuring you have all updates available at this time.)
5.  git checkout -b branchname
6.  git merge master
7.  code . (Provides access to VS Code where you can make and save changes to puppy.md.)
8.  git status (Confirms modifications to puppy.md.)
9.  git add . (Stages changes.)
10. git commit -m “Ticket 123: puppy.md updates”
11. git **push** (This command moves puppy.md updated in your local repository to the remote GitHub environment.)
12. Access GitHub and create a PR specific to this branch.
13. Request PR review and approval.
14. Merge PR into the main branch.
15. Delete your branch.
