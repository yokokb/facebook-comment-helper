# facebook-comment-helper
A tool that helps community managers to find and answer relevant comments in their FB pages

## Licensing
The tool is distributed under the MIT License (https://opensource.org/licenses/MIT)

## Technical details
- Windows 7
- Python 2.7.6

## Installation and Execution
The tool can be installed using the setup.py or as Windows program.

Command line:
```
C:\facebook-comment-helper> python setup.py install
C:\facebook-comment-helper> python ./gui/comment_helper_gui.py
```

Windows program:

After executing the installer (see [installer folder](installer/Output)), 
the tool will be saved in the machine (default location C:\Program Files\FacebookCommentHelper) and a shortcut will be created on the Desktop

Note that the installer has been created for Windows 64-bit. Further information about how to create the installer is available in the see section **Build installer** 

## How to
The tool comes with a simple GUI that needs a Facebook token and a target page.

Then, by clicking on the button "Launch Browser", a tab in the default browser will open and point to facebook.com 
to allow the user to log in.

Once the user is logged in, he can click the "Get Next Comment" button. The tool will look for the next 
**relevant comment*** and show it in the browser. At that moment, the user will be able to answear/react to the comment.

At any moment the user can close the tool by clicking on the exit button of the GUI.

**Note that a relevant comment is a comment that contains a photo or a video*

**A short tutorial showing how to use the tool is available in the [docs folder](docs)**

## Limitations
Currently the tool does not look for relevant comments in nested comment replies.

## Build installer
In order to build an installer, you need:

- WinPython (https://winpython.github.io/), which is a portable distribution of Python
- Inno Setup (http://www.jrsoftware.org/isinfo.php), which generates an installer for Windows.

### Process:

1. Create a folder named MyApplication in your development machine (ex.: C:\MyApplication\). This folder will be copied to C:\Program Files\MyApplication by the installer.

2. Download and install a WinPython version into MyApplication. For instance, if you download WinPython-64bit-2.7.13.1Zero, you should install it in MyApplication\WinPython-64bit-2.7.13.1Zero.

3. Copy in the folder tools (located in MyApplication\WinPython-64bit-2.7.13.1Zero\tools) the script [setup.py](setup.py) and the folders [gui](gui) and [helper](helper) of this repository.

3. Using the WinPython Command Prompt.exe (located in MyApplication\WinPython-64bit-2.7.13.1Zero), use the setup.py to install facebook-comment-helper. For instance,
```
C:\MyApplication\WinPython-64bit-2.7.13.1Zero\tools\facebook-comment-helper> python setup.py install
```
Note that, in order to reduce the size of the installer, you can also remove Python packages that the tool doesn't needed.

4. Open Inno Setup and write a .iss file like the one in the [installer folder](installer/installer.iss) and execute it. Note that if you want to change the target platform from 32 to 64, just modify **DefaultDirName={pf64}..** with **DefaultDirName={pf32}..**

5. The mysetup.exe will appear in a folder called *Output* where the .iss file has been saved.

