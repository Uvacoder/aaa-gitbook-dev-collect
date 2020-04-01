# Terminal

|  |  |
| :--- | :--- |
| [https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet) | 3/9 |
| [http://zsh.sourceforge.net/Intro/intro\_toc.html](http://zsh.sourceforge.net/Intro/intro_toc.html) | 2/18 |
| [https://ohmyz.sh/](https://ohmyz.sh/) | 2/18 |
| [My Terminal Setup: iTerm2 + Zsh 🔥](https://dev.to/aspittel/my-terminal-setup-iterm2--zsh--30lm) | 2/6 |

* In order for Oh-My-Zsh to work, Zsh must be installed.
  * Please run `zsh --version` to confirm.
  * Expected result: `zsh 5.1.1` or more recent
* Additionally, Zsh should be set as your default shell.
  * Please run `echo $SHELL` from a new terminal to confirm.
  * Expected result: `/usr/bin/zsh` or similar

{% code title="zsh" %}
```bash
sudo vim ~/.zshrc
source ~/.zshrc
open ~/.zshrc
```
{% endcode %}

{% code title="terminal commands" %}
```bash
cd #change directory
pwd #print working directory
ls #list files
echo $SHELL #echo's your terminal/shell
```
{% endcode %}

{% code title="shortform" %}
```bash
i          ##install
--save-dev ##--D
```
{% endcode %}

