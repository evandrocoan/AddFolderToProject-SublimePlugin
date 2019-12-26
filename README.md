Add Folder To Project
=====================

With this plugin you can **open a file in sublime and easily add the file folder to the project**, **add a generic folder (asked by a prompt dialog) to the project** and you can also **copy into the clipboard the path of the file** you're editing **or the path of the file's directory**.

You can also create a new project starting from the opened file in sublime.

I created this plugin because I often edit files in sublime opening it directly from MS Visual Studio (I created the shortcut Alt+S in VS) or with F4 from TotalCommander and I generally find useful having the directory in the project or copying the file path in the clipboard.


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
    wait few seconds until the installation finishes up
1. Now,
    Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    input the following address and press <kbd>Enter</kbd>
    ```
    https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
    ```
1. Go to the menu **`Tools -> Command Palette...
    (Ctrl+Shift+P)`**
1. Type **`Preferences:
    Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    find the following setting on your **`Package Control.sublime-settings`** file:
    ```js
    "channels":
    [
        "https://packagecontrol.io/channel_v3.json",
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
    ],
    ```
1. And,
    change it to the following, i.e.,
    put the **`https://raw.githubusercontent...`** line as first:
    ```js
    "channels":
    [
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
        "https://packagecontrol.io/channel_v3.json",
    ],
    ```
    * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
      you will not install this forked version of the package,
      but the original available on the Package Control default channel **`https://packagecontrol.io...`**
1. Now,
    go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    search for **`AddFolderToProject`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.


Usage
-----
Just right click on the view or open the command panel and choose the operation.

**Add Folders To Project:**
Opens a list of the directories from the root to the file's directory.

![Add Folders To Project](./images/AddFolders.png)

**Add This Folder To Project:**
Add directly the file's directory to the project.

![Add This Folders To Project](./images/AddThisFolder.png)

**Copy File Path**:
![Copy Path](./images/CopyPath.png)

Copies the file path to the clipboard.

**Copy Dir Path**:
Copies the file's dir path to the clipboard.

ToDo
----
1. Add the settings file to allow the user to choose which menu item to visualize both in the righ-click menu and in the operation panel (Ctrl+Shift+P).

ChangeLog
=========
AddFolder - 1.1.1
---------------
- Corrected behavior with no project already opened.

AddFolder - 1.1.0
---------------
- Fixed menu item visibility with file without a phisical path
- If there is no phisical paths now the plugin asks for a custom path
- If a directory already exists in the project it won't be shown in the list dialog
- If the file's directory already exists in the project in the left click menu you'll now see not the "add this folder to project" but a new more useful "remove this folder from poject". Quite self-explaining, I think.
- Now you can create a blank new project starting from the opened file with the command (in the Ctrl+Shift+P Menu) "Create Project from File". This command will open a new sublime window with a new project containing only the file's directory. *I can't try it under OsX* so I just copied two lines of code from another project (thanks to the SideBarEnhancements sublime plugin). *OsX Users: can you please tell me if it works?!*. This will be really appreciated.

AddFolder - 1.0.0
---------------
- First Release
