# Git

|  |  |
| :--- | :--- |
| [Modifying git History \(1/3\) - Amending a Commit in git](https://www.youtube.com/watch?v=ckEyL7gMRbA) | 12/2 |
| [10 Awesome Github Repos Every Web Developer Should Know](https://dev.to/simonholdorf/10-awesome-github-repos-every-web-developer-should-know-27oa?utm_source=digest_mailer&utm_medium=email&utm_campaign=digest_email) | 11/15 |
| [How to rename your default GitHub branch to main](https://gomakethings.com/how-to-rename-your-default-github-branch-to-main/) | 10/31 |
| [How to quickly create a new GitHub Gist or CodePen](https://gomakethings.com/how-to-quickly-create-a-new-github-gist-or-codepen/) | 10/17 |
| [Patterns for writing better git commit messages](https://dev.to/helderburato/patterns-for-writing-better-git-commit-messages-4ba0?utm_source=digest_mailer&utm_medium=email&utm_campaign=digest_email) | 9/13 |
| [Replacing master in git](https://dev.to/damcosset/replacing-master-in-git-2jim) | 6/15 |
| [Git Explained: Proper Team Etiquette](https://dev.to/milu_franz/git-explained-proper-team-etiquette-1od) | 5/27 |
| [https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet) | 3/9 |
| [https://ohshitgit.com/](https://ohshitgit.com/) | 2/26 |
| [WPEngine](https://wpengine.com/git/) |  |
| [Atlassian tutorials](https://www.atlassian.com/git/tutorials) |  |
| [dev.to Crash course](https://dev.to/chrisachard/confused-by-git-here-s-a-git-crash-course-to-fix-that-4cmi) |  |
| [Learn git branching](https://learngitbranching.js.org/) |  |
| [https://github.com/w3c](https://github.com/w3c) |  |
| [try.github.io](https://hashnode.com/util/redirect?url=https://try.github.io/) |  |
| [git-scm.com/book/en/v2](https://git-scm.com/book/en/v2) |  |
| [git-tower.com/learn](https://hashnode.com/util/redirect?url=https://www.git-tower.com/learn/) |  |

### Amend

```bash
$git commit --amend -m 'new commit message'
```

### Branches

```bash
# if you catch yourself having done a bunch of dev in a branch you didn’t mean to
# move all your uncommited changes to a new branch without disturbing the one you were in.

$git checkout -b <new branch name>
```

### Remotes

{% code title="init remove and add git sources" %}
```bash
// initialize a git repo
$ git init

$ git remote rm origin
$ git remote add origin git@github.com:environment/project-name.git
```
{% endcode %}

```bash
git remote -v
git remote add wpeprod git@git.wpengine.com:production/bioinncapital.git
git remote add wpestage git@git.wpengine.com:staging/bioinncapital.git

git remote add wp_dev git@git.wpengine.com:production/devkinective.git
git remote add wp_stage git@git.wpengine.com:production/stagekinective.git
```

