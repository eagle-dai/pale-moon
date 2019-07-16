
Build with Visual Studio 2015
---------------------------------------------------------------------------------------------------
- Make sure visual studio 2015 is installed.
  https://stackoverflow.com/questions/44290672/how-to-download-visual-studio-community-edition-2015-not-2017

- Download and install MozillaBuild to local folder, e.g. C:\mozilla-build
  https://ftp.mozilla.org/pub/mozilla/libraries/win32/MozillaBuildSetup-2.2.0.exe
  
- Copy mybuild/.mozconfig to its parent folder and make necessary changes if needed

- Run in cmd.exe:
  cd C:\mozilla-build
  start-shell-msvc2015-x64.bat

  Run in the new shell:
  cd <repo>
  ./mach build
  ./mach installer

  Errors: 
  1) ERROR: Cannot find mt
     Workaround: export PATH="$PATH:/C/Program Files (x86)/Windows Kits/10/bin/10.0.16299.0/x64"

- Outputs:
  - binary files:
    <repo>\obj-x86_64-w64-mingw32\dist\bin
  - installer:
    <repo>\obj-x86_64-w64-mingw32\dist\palemoon-<version>.win64.installer

	
NOTE
---------------------------------------------------------------------------------------------------
- All my changes are with comment tag string: MYBUILD
