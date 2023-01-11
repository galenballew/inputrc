function timer_start {
  timer=${timer:-$SECONDS}
  TIME_LAST_STARTED=`date +%T`
}

function timer_stop {
  timer_show=$(($SECONDS - $timer))
  time_last_started_show=${TIME_LAST_STARTED}
  unset timer
  unset TIME_LAST_STARTED
}

trap 'timer_start' DEBUG
PROMPT_COMMAND='timer_stop'

PS1='[\[\033[01;35m\]${timer_show}s \t\[\033[00m\] ${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\] \[\033[01;34m\]\w\[\033[00m\]]\n\$ '
