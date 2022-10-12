# Start VM upon start up
1. Include following to PATH environment: %PROGRAMFILES%\Oracle\VirtualBox
1. Press Win+R.
2. Type in "shell:startup"
3. Create cmd- or bat-file:
Vboxmanage startvm "vmname" --type headless
4. Done.
