# Thick Client Testing Methodology


### Major checks:

> Regshot [https://sourceforge.net/projects/regshot/]
- Snapshot registeries before and after installation to check changes

> CFF Explorer [https://ntcore.com/]
- Use CFFexplorer to view information development platform and other information

> Process Explorer [https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer]
- View DEP and ASLR status in Sysinternals > process explorer -> properties
- Check strings tab in process explorer for sensitive information/passwords

> ILspy [https://github.com/icsharpcode/ILSpy]
- Decompile application using ILspy

> Ollydbg/Immunity Debugger [http://www.ollydbg.de/] [https://www.immunityinc.com/products/debugger/]
- Use ollydebug and/or Immunity debugger to understand function calls and do binary analysis (Hard-coded credentials, API Keys, API Endpoints, Comments, Hidden functions)

> SigCheck [https://docs.microsoft.com/en-us/sysinternals/downloads/sigcheck]
- Check for unsigned certificates in Sysinternals > sigcheck64 by using command <path to sigcheck> sigcheck64 -a test.exe

> Echo Mirage [https://sourceforge.net/projects/echomirage.oldbutgold.p/]
- Intercept using echomirage to see for sensitive data transferred over an unencrypted tunnel
- Echomirage - is similar to BurpSuite for thick clients
	- Create new rule for intercept
	- Process - inject - select your exe
	- Post injection, run your exe application 
	- See how data is flowing

> SSL Scan 
- Check weak ciphers of server(s) that the application is connecting to.

> JavaSnoop [https://code.google.com/archive/p/javasnoop/downloads]
- For testing .jar applications use JavaSnoop

> TCPView [https://docs.microsoft.com/en-us/sysinternals/downloads/tcpview]
- Use TCPview to view connections made by application to remote servers

> Procmon [https://docs.microsoft.com/en-us/sysinternals/downloads/procmon]
- Use procmon to see what events are created by application, use filters

> DLLSpy [https://github.com/cyberark/DLLSpy]
- Check for DLLhijacking vulnerability by running DLLspy

### Additional checks :
- View .config file in txt from installed directory to see any sensitive information stored
- Try to brutefirce login of SQL database if the application uses it
- Open Config Files, if Available
- Use Dnspy To See Exe Decompiled Code, Use 32 Bit Dnspy To Decompile 32 Bit Apps Even If Your Pc Is 64 Bits 
- Check For Hardcoded Password
- Check IP Addresses And Other Information Leakage
- Change Part Of Source Code Which Accepts Login And Manipulate It, If Server Responds, Report It
- You May Use Process Monitor To See Where The Data Is Being Sent
- Check Changed In Registry (registry Entries By Exe)
- Post decompiling using ILspy Right Click On Any Function Or Method And Select 'analyse'
- To change A Method, Right Click On Function "edit Method In C#" Compile And Save It