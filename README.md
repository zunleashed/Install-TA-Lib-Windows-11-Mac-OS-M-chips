# Install TA-Lib on Windows 11 64 bit and Mac OS with M series chips

CLAIMER: THERE ARE NO guarantees on the correctness of the following content as they are a summary of the general process. Please perform your own due diligence to ensure applicability, correctness, and other related licensure limitations. 

As of 10.6.2024, Numpy 1.26.4 works with TA-Lib on both Windows and Mac OS

Create an isolated virtual environment (i.e. python -m venv venv) to keep Numpy older version separated from other projects requiring updated Numpy.

# Mac OS M series chip

Install Homebrew

launch a regular terminal {bash/VS Code terminal/PowerShell/etc.} for venv and pip instal operations

  brew install ta-lib
  
  $ export TA_INCLUDE_PATH="$(brew --prefix ta-lib)/include"
  
  $ export TA_LIBRARY_PATH="$(brew --prefix ta-lib)/lib"
  
  -- using {cd} commands, navigate to where venv shall be housed --
  
  mkdir folder_name
  
  cd folder_name
  
  python -m venv venvi
  
  source venvi/bin/activate
  
  which python 
  
  -- result to show the path of this new venv --
  
  which pip
  
  -- result to show the path of this new venv --
  
  -- optionally install other useful libraries --
  
  pip instal pandas scipy matplotlib
  
  pip install TA-Lib
  
  pip uninstall numpy
  
  pip cache purge
  
  pip install numpy==1.26.4
  

if using VS Code

  -- open directory housing the vevn type the following in the top center search bar --
  
  > python: select interpreter

  select python interpreter from the newly made venv
  

# Windows 11 64-bit

General description: need to download the C precompiled ta-lib file, unzip to C:\, and use microsoft Visual Studio installer and 'x64 Native Tools Command Prompt for VS 2022' to install ta-lib (analogous to 'brew install ta-lib'). then activate isolated venv, and pip install TA-Lib.

download the {ta-lib-0.4.0-msvc.zip} from {https://pypi.org/project/TA-Lib/} or {https://ta-lib.org/}

unzip and move 'ta-lib' folder to {C:\} or unzip to the {C:\} destination.

download Visual Studio Installer: {https://visualstudio.microsoft.com/vs/community/}

from various main suite of install packages, only select {Desktop development with C++} 

select the following specific installs, this download/install will take a while...:

  MSVC v143 - VS 2022 C++ x64/x86 build...
  
  C++ ATL for latest v143 build tools (x86 &...
  
  C++ Build Insights
  
  C++ profiling tools
  
  C++ CMake tools for Windows
  
  C++ AddressSanitizer
  
  Windows 11 SDK -- all the options for Windows 11 SDK --
  
  C++ MFC for latest v143 build tools...
  
  C++ Modules for v143 build tools...
  
after C++ tools are completely installed

from windows search explorer open the x64 native command prompt by searching {x64 Native Tools Command Prompt for VS 2022}

> cd "C:\ta-lib\c\make\cdr\win32\msvc" 

> nmake

-- this will take a bit of time --

launch a regular terminal {bash/VS Code terminal/PowerShell/etc.} for venv and pip instal operations

 -- using {cd} commands, navigate to where venv shall be housed --
 
 -- following commands are in bash syntax, but one can find equivalent in powershell, cmd, etc....--
 
  mkdir folder_name
  
  cd folder_name
  
  python -m venv venvi
  
  source venvi/bin/activate
  
  which python 
 
  -- result to show the path of this new venv --
  
  which pip
 
  -- result to show the path of this new venv --
  
  -- optionally install other useful libraries --
  
  pip install pandas scipy matplotlib
  
  pip install TA-Lib
  
  pip uninstall numpy
  
  pip cache purge
  pip install numpy==1.26.4





