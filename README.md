# Thick-client-testing
This is the methodology that I use for thick client testing


Things to test in Thick client(EXE) testing:
	Snapshot registeries before and after installation to check changes
	Use CFFexplorer to view information development platform and other information
	View DEP and ASLR status in Sysinternals > process explorer -> properties
	Check strings tab in process explorer for sensitive information/passwords
	Check for unsigned certificates in Sysinternals > sigcheck64 by using command <path to sigcheck> sigcheck64 -a test.exe
	Intercept using echomirage to see for sensitive data transferred over an unencrypted tunnel
	For testing .jar applications use JavaSnoop
	Use TCPview to view connections made by application to remote servers
	Use procmon to see what events are created by application, use filters
	Check for DLLhijacking vulnerability by running DLLspy
	View .config file in txt from installed directory to see any sensitive information stored
	Use ollydebug and/or Immunity debugger to understand function calls and do binary analysis (Hard-coded credentials, API Keys, API Endpoints, Comments, Hidden functions)
	Decompile application using ILspy
	Try to login to SQL database if the application uses it


Popular usable tools:
Ecomirage
Wireshark
Sslscan - weak ciphers
Regshot
Oledebug
Sysinternals toolkit - malware analysis
Dependency walker - dependency components
Dllhijacking
Immunity debugger

Echomirage:
it is like burpsuite for thick clients
create new rule for intercept
process - inject - select your exe
echo mirage will inject, run your exe, see how the data is flowing
