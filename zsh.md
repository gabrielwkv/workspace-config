# Oh My ZSH

### Setup process to install zsh with agnoster theme

<br>

<p>Initially go to the <a href="https://ohmyz.sh ">zsh</a> website, and do the installation process with <code>curl</code> or <code>wget</code></p>

<p>Initially it will come configured with robbyrussell theme, we will change to agnoster</p>

open the <code>~/.zshrc</code> and edit the line ``ZSH_THEME="robbyrussell"`` for ``ZSH_THEME="agnoster"``

<p>To remove the machine name and leave only the paths, change this:<p>

```sh
prompt_dir() {
  prompt_segment blue black '%~'
}
```

<p>for this:</p>

```sh
prompt_dir() {
  prompt_segment blue black '%c'
}
```

<p>and this:</p>

```sh
prompt_context() {
  if [[ "$USERNAME" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment black default "%(!.%{%F{yellow}%}.)%n@%m"
  fi
}
```
<p>for this:</p>

```sh
prompt_context() {
  local user=`whoami`

  if [[ "$user" != "$DEFAULT_USER" || -n "$SSH_CONNECTION" ]]; then
    # prompt_segment $PRIMARY_FG default " %(!.%{%F{yellow}%}.)$user@%m "
  fi
}
```

<p>To finish, let's install some plugins to make zsh more turbocharged</p>

<p>let's start by installing the packages, paste in your terminal the link and waiting install:</p>

``
sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"
``

<p>open <code>~/.zshrc</code> in end line paste the code</p>

```
zinit light zdharma/fast-syntax-highlighting
zinit light zsh-users/zsh-autosuggestions
zinit light zsh-users/zsh-completions
```

<p>Finally, restart the terminal to install the plugins, and enjoy!</p>