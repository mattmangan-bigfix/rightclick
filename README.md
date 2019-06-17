# rightclick
BigFix Right Click Options - Linux (RCOL)

After seeing all of the wonderful right click options for Windows endpoints, I figured it would be nice to have some that focus on Linux. For now the three that are in here (restart client, open putty session, tail latest log) are just the start. I need to create a registry entry for the top command. This will be added shortly.

Prerequisites
---------------
Prior to using the RCOL, you will need to create a new property.

registration_ip: registration address of client

When implementing right click options, the '.reg' files need to be modified to reflect your *local* environment. As seen below, the registry settings are local to the user that does the import. Take note of the "ShellCommandRelevance", this is where you modify the path to where the remote command text files live. 


[HKEY_CURRENT_USER\Software\BigFix\Enterprise Console\Settings\ComputerListContextMenuExtensions\Linux - Tail Latest BESClient Log]
"MaxComputerSetSize"=dword:00000001
"MenuDisplayName"="&Linux - Tail latest BESClient Log"
"ShellCommandRelevance"="\"plink.exe -m C:\\path\\to\\remote\\commands\\newtail.txt \"&  (value of property result whose (name of property of it = \"registration_ip\" ) of current computer )"



