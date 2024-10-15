about variables and expensions

ex 0 create temprorary alias
alias ls="rm *"

ex 1 user is the current user
echo "hello ${USER:-$(whoami)}"

la solution la plus simple est :   echo $USER


