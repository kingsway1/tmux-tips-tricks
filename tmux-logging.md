# TMUX prompt to enable tmux logging

Set up streamlined TMUX logging.

- Set up streamlined TMUX logging.

When a new pane is opened, the user is prompted to enable logging (default N). If enabled, the log is saved in the $HOME directory in the format {session-name}-{window-index}-{pane-index}-{day}-{month}-{year}.log

First things first, ensure that you have set up tmux-logging. Installation and set up can be found here https://github.com/tmux-plugins/tmux-logging.

#Enabling a logging promt in TMUX.

To set up the location & format of the logs, edit the '.tmux/plugins/tmux-logging/scripts/variables.sh'.

filename_suffix="#{session_name}-#{window_index}-#{pane_index}-%d-%m-%Y.log"
