# Remotes

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

