
export VIRTUAL_ENV_DISABLE_PROMPT=1
source .virtualenv/bin/activate
export GITAWAREPROMPT=~/.bash/git-aware-prompt
source "${GITAWAREPROMPT}/main.sh"
source ~/.git-completion.bash
export PS1="\w \[$txtcyn\]\$git_branch\[$txtred\]\$git_dirty\[$txtrst\]😎 "


alias ls='ls -GpF -h'
alias grep='grep -a --color'
alias inscreen='echo $STY'
alias history='cat ~/.bash_history'
HISTFILESIZE=500000
alias jsonformat='python -m json.tool'
alias cyphertracer='hexdump -C /dev/random | grep --color=always "ca fe"'

if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi


function catheader()
{
head -n1 ${1} | tr "\t" "\n" | nl
}

calc () {
    bc -l <<< "$@"
}

