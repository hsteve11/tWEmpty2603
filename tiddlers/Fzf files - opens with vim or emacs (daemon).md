`fo() {
  local ed file ans
  ed="$1"

  file=$(fzf) || return

  case "$ed" in
    v|vim)
      vim "$file"
      return
      ;;
    e|emacs)
      emacsclient -n "$file"
      return
      ;;
  esac

  printf "[v]im or [e]macs? "
  read -k 1 ans   # zsh: -k 1 = read 1 keypress
  echo

  case "$ans" in
    v) vim "$file" ;;
    e) emacsclient -n "$file" ;;
  esac
}
`