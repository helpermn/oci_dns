# oci_dns

For GIT add a priv key to ssh agent:
- .bashrc updated with:
####################################################################
# SSH AGENT
if pgrep -U $(whoami) ssh-agent 2>/dev/null ; then
        declare -x SSH_AGENT_PID="$(pgrep -U $(whoami) ssh-agent)"
        declare -x SSH_AUTH_SOCK="/home/opc/.ssh/sshagent";
else
        eval $(ssh-agent -a ~/.ssh/sshagent -t 86400 -s)
fi
####################################################################
- issue in a terminal:
    ssh-add ~/.ssh/github

For Ansible to access a priv key:
- configure Ansible in Visual Studio Code:
    ansible.ansible.reuseTerminal = Yes
- issue in a terminal:
    read -s OCI_USER_KEY_PASS_PHRASE; export OCI_USER_KEY_PASS_PHRASE