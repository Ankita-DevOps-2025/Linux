# What are Environment Variables?
Environment Variables (Env Variables) are defined as something that allows you to store data in memory that can be easily accessed by any program or script running from the shell.

store information about the shell session and the working environment
-> VAR_NAME=value

# How to See Existing Environment Variables (Env Variables)?
printenv
env

# How to See a Specific Environment Variable (Env Variable)?
printenv HOME
echo $HOME

# Environment Variable Types in Bash
Global variables
Local variables

# How to create local user-defined variables that are visible within your shell process
MY_VAR=Hello  /  MY_VAR="hello world" (only limited to current shell)
echo $MY_VAR
* but if you now run env | grep MY_VAR  it will not show you in list
to remove this variable => unset MY_VAR


- to save it use "export"
eg -> export MYVAR=hello  

you will able to see it in env/printenv comand but still if you just change the terminal it will be no longer there, it is still a local env variable

# set Env Var using profile
- Set Env variable permanent for user
Edit ~/.profile (for Ubuntu).
Edit ~/.bash_profile (for Centos).

- And set variable
export MYVAR=VALUE
source ~/.profile(to apply immeediately)

- it will only be for that sepecfic user only for which you are login 
- it will still not appear in new tab/terminal you need to run the source source ~/.profile

- to use it in new terminal make changes in ~/.bashrc file and then run "source ~/.bashrc"

# Set Permanent Environment Variables for All Users
Edit /etc/profile/
Set variable: export MYVAR=VALUE.
To apply the changes immediately: source /etc/profile/.




