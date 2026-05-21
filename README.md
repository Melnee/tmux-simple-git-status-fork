# Tmux simple git status

Prints current pane git branch and uncommitted changes (if available). My updates include emoji, and pipe separator. Also, added two more statuses: if your branch is behind, or if your branch is ahead, of the remote!

<img width="1234" height="383" alt="image" src="https://github.com/user-attachments/assets/43b93cc6-b1ca-47cb-ad03-a4533bc4501e" />


## Installation
### Installation with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

    set -g @plugin 'kristijanhusak/tmux-simple-git-status'

Add `#{simple_git_status}` to your `status-left` or `status-right` tmux option:

```
set -g status-left "#{simple_git_status}"
```

Hit `prefix + I` to fetch the plugin and source it.

### Manual Installation

Clone the repo:

    $ git clone https://github.com/kristijanhusak/tmux-simple-git-status ~/clone/path

Add this line to the bottom of `.tmux.conf`:

    run-shell ~/clone/path/simple_git_status.tmux

Add `#{simple_git_status}` to your `status-left` or `status-right` tmux option:

```
set -g status-left "#{simple_git_status}"
```

Reload TMUX environment:

    $ tmux source-file ~/.tmux.conf

## FAQ

*Q: Status is not updating in real time.*

A: Frequency of update depends on tmux `status-interval` option. To refresh the status every 5 seconds, add `set -g status-interval 5` to your `.tmux.conf`

*Q: There is a space before and after the status.*

A: Those are added in order to allow easier styling and highlighting (like on screenshot). If you would add an empty space by yourself, you would get empty blocks in your statusline that doesn't hold anything. If you really want it to be removed, please file an issue.


Fork Changes:
👻 = untracked (aka new files)
➕ = insertions
➖ = deletions
🔧 = modified
⏫ = your branch is head of remote
⏬ = your branch is behind remote
🚀 = staged changes to commit
