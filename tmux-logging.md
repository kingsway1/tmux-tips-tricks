# TMUX - Prompt to enable tmux-logging

Set up streamlined TMUX logging.

- Set up streamlined TMUX logging.

When a new pane is opened, the user is prompted to enable logging (default N). If enabled, the log is saved in the $HOME directory in the format {session-name}-{window-index}-{pane-index}-{day}-{month}-{year}.log

First things first, ensure that you have set up tmux-logging. Installation and set up can be found here: 

[https://github.com/tmux-plugins/tmux-logging]

# Enabling a logging prompt in TMUX


## Set up the location & format of the logs 

Edit the '.tmux/plugins/tmux-logging/scripts/variables.sh'


### Set location of logs
```default_logging_path="$HOME/logging"```

### File format of tmux logs
```filename_suffix="#{session_name}-#{window_index}-#{pane_index}-%d-%m-%Y.log"```

## Edit .profile to enable a [Y/n] prompt for TMUX logging

```
if [ "$TMUX" ] ; then
read -r -p "Enable terminal logging? [y/N] " response
case "$response" in
    [yY][eE][sS]|[yY])
    tmux run-shell "/$HOME/.tmux/plugins/tmux-logging/scripts/toggle_logging.sh"
    ;;
   *)
    ;;
esac
fi
```
