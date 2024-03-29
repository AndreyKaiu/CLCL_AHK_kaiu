CLCL version 2.1.3.5
--

■ Introduction
CLCL is a program that keeps clipboard history.

■ Functions
・Supports multiple clipboard formats
・Frequently used phrases can be registered hierarchically
・Freely customizable menu display via hotkeys
・Automatic insertion of history and registered items (Templates) selected from the menu
・Reduced the display of images in the menu
・Show tooltips on the menu
・You can set the format to save in history and whether it will be saved on exit
・You can set the window to save or not save history
・Paste key can be set for each window
・History is automatically saved at the end and restored on next launch
・There is no limit to the maximum number of records that can be saved in the history
・Display and edit the history and registered items (Templates) in a viewer similar to Explorer
・Expand functionality by adding plugins
・Compatible with Unicode

■ Installation
It works on Windows XP or later OS versions.

Run the downloaded file to install CLCL.
If you installed CLCL before, then remove it from the control panel.
Before deleting, check that you have exited CLCL and that it is not hanging in the tray.

The data is stored in the following folders. (For Windows 10)
    C:\Users\(username)\AppData\Local\CLCL

To save data in the same location as CLCL.exe, set clcl_app.ini as follows.
Run CLCL with:

[GENERAL]
portable=1

- The file from version 2.1.3.2 comes with the setting immediately for portability (clcl_app.ini contains [GENERAL] portable=1)

■ Download
When you run CLCL, a paperclip icon will appear in the task tray (the area with a clock in the corner of the taskbar).
Clicking this icon on the taskbar will display a menu.
By default, the menu displays history in ascending order.
The menu can be customized in the settings.

Right-click the icon on the taskbar to display the viewer.
On the left side of the viewer there is a tree that displays the history and registered elements (Templates).
The right part of the viewer displays and edits the contents of the history and registered items.
The edited content will be reflected in the element when focus moves.
Some formats cannot be edited.
The current contents of the clipboard cannot be edited.

The "Clipboard" at the top of the tree is the current contents of the clipboard.
"History" in the tree is a list of history.
"Templates" in the tree is a list of registered items (fixed phrases, etc.).

   ┌─■ Clipboard - current contents of the clipboard
   │ ├─□ TEXT - format in the current clipboard
   │ ├─□ LOCALE
   │ └─□ OEM TEXT
   │
   ├─■ History - clipboard history
   │ ├─□ (BITMAP) - history element
   │ │ ├─□ BITMAP - formatting history elements
   │ │ └─□ DIB
   │ │
   │ ├─□ Hi...
   │ │ └─□ TEXT
   │ │
   │ ├─□ Today...
   │ └─□ (BITMAP)
   │
   └─■ Template - Registered Items
       │
       ├─■ Folder - Folder
       │ ├─□ Address...
       │ └─□ (BITMAP)
       │
       └─□ http://www... - registered element
           └─□ TEXT - format in the registered element
  
  
■ Clipboard
・What is a clipboard?
   The clipboard is an area for exchanging information between different applications.
   For example, you can paste characters copied in Notepad into Word, etc., but this is because an area called the clipboard is used.

・Clipboard Format
   The clipboard can store multiple formats at the same time.
   For example, if you copy the text in notepad:
     ・UNICODE TEXT
     ・LOCALE
     ・TEXT
     ・OEM TEXT
   4 formats are entered into the clipboard (for Windows 10)
   Even more formats will be sent to the clipboard if you copy to Excel or Access

   Default CLCL
     ・UNICODE TEXT - text
     ・BITMAP - bitmap
     ・DROP FILE LIST - Files are now in history.
   An additional "filter" allows you to save other formats in the history.
   
■ History
This is the history of the data copied to the clipboard.
The new copied data is added to the beginning of the history.

One history element contains multiple clipboard formats. The clipboard format with the highest priority, which is specified in the "Format" option, is displayed in the menu and viewer.

The number of stories remains the same as set in the "History" option.
Clipboard formats are only added to the history if they are configured to be added in the "Filter" option.

■ Templates (registered items)
You can register frequently used data such as fixed phrases in registered items.
You can add folders to create hierarchies and item names.

To add a registration item, open the viewer, select the item in the history, and choose Add to Registration Item (Templates) from the menu.
Select the folder you want to add to the tree and select New from the menu to create an item by reading the contents from an empty item or file.

To add a folder, open the viewer and right-click on the location you want to add to the registered item and select "Create Folder".

To rename a folder or item, open the viewer, select the item you want to change, open the context menu, and select Rename.
"Clear name" clears the set name and displays the content of the element as the name.
If the element name is set to "-", it will be displayed as a delimiter in the menu. Ignore any formatting or data within the element.
If you add & to the name, the next character will be used as the menu shortcut key. If you want & to appear on the menu itself, use &&.

You can assign a hotkey to a registered item by right-clicking a registered item to bring up the menu and selecting "Hotkey Settings". Pressing this key will send the registration item directly to the clipboard without displaying a menu, and will paste it directly if the "Paste" function is enabled.
Registered hotkeys can be checked in the list display part of the viewer. If you select other registered items, they will be displayed in the status bar.

The number of registered items or clipboard format is not limited.

■ Send to clipboard
There are several ways to send history and registered items to the clipboard.
・Press the taskbar to display the menu.
   When you select a story or a registered element (Template) from it, the data is sent to the clipboard and automatically pasted into the active window.

・Press the hot key (Alt + C in the initial state) to bring up the menu.
   When you select a story or a registered item from it, the data is sent to the clipboard and automatically pasted into the active window (do not paste when holding Shift)..

・Select an item in the viewer and display the context menu.
   Select "Send to Clipboard" to send the selected item to the clipboard.

■ Menu
The menu items displayed by the taskbar or hotkeys are set in the "Action" option.
Customize the menu display in the "Menu" option.

If you hover over items in the history or registered menu items, the detailed content will be displayed as a tooltip at the mouse position. A tooltip appears below a menu item when the item is selected using the keyboard.

If you right-click an item in the menu history or a registered item (Templates), the registered tools will be displayed in the menu, and the tool selected for the item will be executed and sent to the clipboard.
To call the Tools menu using the keyboard, press Ctrl+Enter on the active menu.

The history and registered items display the menu items according to the "Menu Text Display Format" option. Displayed numbers start at 0, but if you want to change the start value, set the start number between % and a letter.
      example:
          %0d -> 0,1,2,3...
          %8x -> 8,9,a,b...
          %1n -> 1,2,3...8,9,0,1,2...
          %10B -> K,L,M,N...
        
■ Operation
You can set the behavior when a hotkey is pressed or when an icon is clicked on the taskbar in the Action option.

If the action in the Edit Action section is set to Menu, set the menu items to be displayed in the menu settings at the bottom of the screen.

The call method sets how to invoke the specified behavior.
If a "hot key" is specified, set the call key.
"Ctrl + Ctrl", "Shift + Shift", and "Alt + Alt" invoke the specified action when the key is pressed twice.

"Insert" can be set by specifying a menu for the action.
"Paste" automatically dispatches a paste action to the app you're working on when you select an item in the menu.
If you hold the Shift key while selecting a menu item, it will only send it to the clipboard without pasting.

Set menu for action, hotkey, Ctrl+Ctrl, Shift+Shift, Alt+Alt.
You can set "Show at cursor position" - displays the menu at the editor's cursor position. If not set, the menu will be displayed at the mouse position.

You can set the display range by specifying a menu for an action and selecting a story for an element. Specify the display range from 1 to the number of records to keep in the history. Specifying 0 as the start number has the same meaning as specifying 1, and specifying 0 as the end number has the same meaning as specifying the number of records to keep in the history.
Nothing is displayed if the end number is less than the start number. If the end number is greater than the number of records to be saved, only the number of records to be saved will be displayed.
        
■ Clipboard Format
CLCL can handle all clipboard formats, but unregistered clipboard formats appear as binary dumps in the viewer.

Register the clipboard format in the "Format" option. The one registered above is given priority, and the clipboard format with the highest priority among items is displayed in the menu and viewer.

The registration specifies the format name and the handling of DLL headers and functions. If you don't specify a DLL and click the function header select button, a list of built-in function headers will be displayed.
For example, among clipboard formats, when copying to Excel, CSV is used as text.
If you want to process
   Format Name: CSV
   dll:
   Function header: text_
will be treated as text in menus and viewers.

■ Filter
Set the "Filter" option to select the clipboard format that will be added to the history.

If you select "Add all formats to history", clipboard formats other than those set as exceptions will be added to the history.
If you select "Exclude all formats from history", only those clipboard formats that are set as optional will be added to the history.

You can set a limit on the size of the clipboard format added to the filter when it is added to history. Do not add data to the history that exceeds the set limit.

If you set "Don't Save" to the clipboard format that is set as an optional filter, it will not be saved to file when CLCL terminates.
For example, you can add text and bitmaps to a story and keep only the text.


■ Window settings
If you want to change the behavior of CLCL depending on the application you are using, set the window and behavior to the "Window" option.

Specifies the window title and class name, and can use "*" as any character.
For example, for Notepad,
   Name: * - Notepad
   Class name: Notepad
will change the behavior of CLCL when notepad is active.
You must enter either a title or a class name, and if you do not enter it, it will have the same meaning as specifying only "*".

・Do not add to history
   Copy operations in the installed window will not be added to the history.
   For apps that cause problems by putting them in history, specifying this setting will cause copies from that app to be ignored.

・Do not set focus
   Prevents focus from being set once activated in the specified window.
   When pasting the selected menu item, the focus moves somewhere, and if you can't paste normally, specifying this option may work fine.

・Paste even if the tool is canceled
   If you cancel an operation with a cancelable tool, it will usually not be pasted after that, but if you specify this option, it will be pasted even if you cancel.
   If you set the copy key as the cut key in the key settings for each window, specifying this option will prevent characters from disappearing even if you cancel the tool.

■ Setting keys for each window
Select history or registered items with hotkeys and automatically send the paste key to the window for the paste behavior.
By default, Ctrl+V is sent to all windows, but depending on the window, the insert key may be a different key.

When calling a tool with a hotkey, the copy key (Ctrl+C) is sent to the window to perform the operation "Copy -> Process Tool -> Paste".

The key for copying and pasting for each window is set in the "Key" option.
Set the title and class name of the window you want to set and set the copy and paste keys.

The copy and paste keys use the default key settings if they are not set.

You can set multiple keys for one window. If you install more than one, the keys will be sent in the order listed above.

■ Tools (plugins)
Use the "Tools" option to process the history and logged data of an element or to extend the functionality of CLCL.

The choice of DLL and function name automatically sets the name of the tool and under what conditions it is executed (call type).
The Action Menu call type includes execution from the menu set in the option action.
The call type "View" allows execution from the "Tools" menu of the viewer.

The send copy and paste function sends a copy to the active window, runs the tool on the copied data, and pastes the result into the active window.
If this option is not checked, the tool will work with the most recent element in the history and send it to the clipboard. In the tool menu that appears when you right-click an item in the action menu, the tool is executed on the selected item and sent to the clipboard.
If "paste" is not enabled in the behavior settings, it will not be pasted after copying and running the tool.

When you drag a DLL into the Registered Tools List window, a list of DLL tools that can be registered is displayed, and you can select multiple tools and register them all at once.
(For a complete description of each tool, see the text files located in the "tool_dll", "format_dll" folders, and if you have the source code, see the "CLCLPlugin" folder)

■ Command line
You can specify the command line when starting CLCL to specify the operation after starting.
If CLCL is already running, the command will be sent to the already running CLCL.

[format]
CLCL.exe [/vownx]
   /v viewer
   /w view clipboard
   /n cancel clipboard browsing
   /x exit
  
■ Special Thanks
K.Takata ( http://webs.to/ken/ )

■ Update history
・Version 2.1.3.4 -> Version 2.1.3.5 (kaiu branch)
- A menu with actions can be shown immediately with the active item specified as a number counted from above (if <0, then from below).

・Version 2.1.3.3 -> Version 2.1.3.4 (kaiu branch)
- The position of the selection in fields like ComboBoxes that allow you to edit data is remembered, but they reset the focus of the selection using Alt+C.
- Ability to remember the selection position in other fields (Options window, “Menu” tab).
- After dragging a word into some other program, you can set the right key press and the space key press, which makes it easier to enter words using this method (the other program becomes active forcibly, since for some reason Notepad++ does not do this). This function can be enabled in the options window, “Viewer” tab.

・Version 2.1.3.2 -> Version 2.1.3.3 (kaiu branch)
- The options window is now always displayed on top of all windows, since CLCL can be on top of all windows.
- Fixed bug with CLCL status indication when full data was reloaded.
- Ctrl+Shift+Click allows you not to execute the history, but to open the viewer immediately at this point for editing (copying as by Shift is left).
- Fixed keyboard control in the menu by "Ctrl + Enter" (showing the tool menu or inserting and reopening the menu).
- Fixed bug with string saving in plugins "tool_text.dll" and "tool_find.dll" when the string contained spaces at the end.

・Version 2.1.3.1 -> Version 2.1.3.2 (kaiu branch)
- File version is now written with 4 characters, example: 2.1.3.2
- In the menu of the program "Help" the item "View help" (F1) has been added, which will open the file "readme_en.txt" (or readme_XX.txt where XX is the designation of the program language).
- Hotkeys for some actions have been added to the program menu.
- Added toggle button "Watch clipboard" (F9) to the toolbar.
- Added toggle button "Above all windows" (F12) with custom icon on the toolbar. Now there is no need to use a plugin for this feature.
- In the "View" menu, it is possible to set the display of control characters (space, tab, line feed) in order to more accurately see the difference in the copied lines.
- Changed the icon of the program. With a yellow background if "Watch clipboard", otherwise a gray background with a red circle (the red circle is now set to the application icon). The icon for "CLCLSet.exe" is made in color, with the inscription "CLCL" (so far, the icons are everywhere as they were in 16 colors, so in theory there should be no problems on the most ancient monitors).
- Now the program reacts more correctly to program scaling in Windows versions less than 8.1. Icons have been changed so that a better visual effect can be realized.
- "Tools" has been added to the context menu on the clipboard item, since it is logical to find the function in it to clear the clipboard.
- Changed for the Russian version calling templates from the "Ш" key to a space (it's more convenient even than R or T). While one hand presses Alt + C, the other is already ready to press the spacebar and then you do not need to reach for R, but immediately to the desired number or character that will launch the menu item.
- If clipboard tracking is disabled, and tools require copy and paste functionality, then the context menu will say "off clcl!" in the names of these tools. An additional reminder to let you know that the tool won't work properly and requires clipboard tracking to be enabled.
- Clicking the right mouse button on a context menu item now performs either the function of showing a tool or pasting and re-showing the menu (without copying to history, for quick various pastings in a row). It is possible to select one of these two functions and by "Ctrl + right-click".
- If in the history parameters it is worth "delete when copying to the clipboard" and clipboard tracking is turned off, then only deletion from the history occurred and this did not allow duplicate entry of the same value (but you cannot copy it to the history). I had to change the algorithm so that if clipboard tracking is turned off, it does not delete when copying to the clipboard.
- The selected inactive item in the history tree is now shown in blue font color to make it easier to find with a glance, otherwise the faint shade of blue background on some computers was not always clearly visible.

- The options window is now always displayed in the center of the desktop. The last page on which “OK” was clicked is remembered, so that later, when called, it will be shown immediately.
- In the options window, you can move items by Alt+Up(Down), as it works for the main CLCL window.
- In the "History" parameters, the flag "When activated, do not add the current clipboard to the history" has been added. If you turned off "Monitor the clipboard" and copied some personal correspondence to the clipboard, then the subsequent inclusion of CLCL should not add your personal data to the History without your permission.
- In the options, if you have selected a path to a file that is in the CLCL folder, then the path will be shown relative, not absolute. Absolute paths make it difficult to transfer a portable program to another computer. In this regard, it is preferable to keep all your DLLs, icons or some other useful scripts in one place, that is, in the CLCL folder.
- Changes in the size of columns in tables are remembered, as it is more convenient for the user (the width is at least 10 pixels, but you can change #define MIN_COL_SIZE_LISTVIEW 10 in the program code).
- Possibility to set in the parameters to force switching of the menu language to ENG, so that all accelerators & format %A were active in any other input language.
- Changed default format for menu numbering from "&%1d. %t" to "&%1C. %t" (at the beginning of the number from 1 to 9 and then the letters of the English language).
- If the plugin has no parameters (the developer commented in the .def file), then the plugin properties button will not be active.
- There can be several identical plug-ins in the program, but the properties of the file are the same (common for each identical plug-in function), and for differences it is necessary to change the command line. The format of the command line is not always clear, and to simplify it, it is now possible to fill in the command line by the button of the usual properties (the plugin should be able to), and if it is empty, then this is considered as common properties. In order to immediately see which properties will work (from the command line or general ones), the “•” sign is added to the beginning of the name of the button with the property (the “?•” is added if there is a ? sign at the beginning of the command line, which can indicate that the user will be shown a dialog box to select options).
- Default settings: for actions, the left mouse button goes first, then the right one (since the reading order is familiar from left to right). Added to these actions the menu item "Watch clipboard". By default, the “show tools on the right button” flag (show_tool_menu) is disabled in the menu settings, since the tools may not be installed at all, and the new “insert and re-show menu” function is more convenient when without the Ctrl + combination. The default menu width is 250, as the previous 200 isn't quite enough.

- Fixed "alloc_copy_n" function error from "Memory.c" when not copying the last character with "lstrcpyn".
- Added relative path for sound file in tool_utl plugin. The selected file is played immediately. (added 3 identical files with different volume)
- The "ztop" and "unztop" functions have been removed from the tool_utl plugin, since CLCL already knows how to do this from version 2.1.3.2.
- In the tool_utl plugin, the code has been changed so that a call from the context menu returns the focus again to the window that was being worked on.
- In the tool_find plugin, the ability to set the flag for reopening the window has been added. The window can remember its position on the screen while working with the program (until the program is reopened).
- In the tool_find plugin, the ability to select previously entered strings that have already been searched has been added.
- In the tool_text plugin, in the text editing function, you can set the window font using the settings in the tool_text.ini file. The window can remember its height, width, and position on the screen while working with the program (until the program is reopened).
- In the tool_text plugin, in the quoting functions (quote, unquote), it is possible to select from the drop-down list the previously entered character (string) of the quotation. The window can remember its position on the screen while working with the program (until the program is reopened).
- In the tool_text plugin, in the function to remove line breaks (delete_crlf), you can set the command 1 - remove leading spaces, 0 - do not delete, ? - ask when calling. The window can remember its position on the screen while working with the program (until the program is reopened).
- In the tool_text plugin, in the text insertion function (put_text), it is possible to select previously entered lines from the drop-down list. The window can remember its position on the screen while working with the program (until the program is reopened).
- In the tool_text plugin, in the function of combining texts (join_text), you can set the command ? - ask when calling. You can choose to merge text in reverse order. The window can remember its position on the screen while working with the program (until the program is reopened).
- Added 3 plugins: "tool_bitmap", "fmt_metafile", "fmt_rtf".
- It was decided not to litter the main location of the program with files related to plugins and create a special folder for them "tool_dll" (for tools) and "format_dll" (for formats).
- Individual actions can now set the paste keys as the specified window (from the "Keys" tab). This is necessary so that some templates can be intercepted by third-party programs. See http://forum.ru-board.com/topic.cgi?forum=5&topic=50494&start=0 "CLCL_AHK - clipboard manager plus advanced text processing with Autohotkey and AutoIt"

? The problem with a slight slowdown of Alt + C in the NOTEPAD ++ program has not been resolved if the main menu is quickly accessed by pressing the C key (different interface languages have their own input accelerators). Disabling the Alt+C hotkey in the NOTEPAD++ program itself does not solve the problem. You can solve the problem by editing the translation of the program menu.


・Version 2.1.3 -> Version 2.1.3.1 (kaiu branch)
   ・The source code has been converted to "UTF-16 LE BOM" encoding, and Russian and English translations have been created wherever necessary. Introduced version description even for DLL. All code has been tested to build in "Microsoft Visual Studio Community 2022" (since it's free for free software) and has been built on Windows 7. Tested to work on Windows XP.
   ・About the program wrote, who is the author of the translation.
   ・The program version is written in the header
   ・Added the ability to escape characters (\r, \n, \t) to the "Insert text (before and after selection)" function in the "tool_text" plugin; added the ability to "set a gap between concatenated texts as a single space" to the "Text Concatenation" function.

・Version 2.1.2 -> Version 2.1.3
   ・Changed the system tray icon when the clipboard is not controlled.
   ・Improved the up and down buttons for setting.
   ・Improved that when the menu is displayed, the main screen is not displayed.

・Version 2.1.1 -> Version 2.1.2
   ・Drag-and-drop scrolling in image format (BITMAP, DIB) is enabled.

・Version 2.1.0 -> Version 2.1.1
   ・Added the function to copy the file name and file path in the file format.
   ・Added option to put settings and data in the same location as CLCL.exe.

・Version 2.0.3 -> Version 2.1.0
   ・High DPI supported.
   ・Supports PNG and JPEG to save files in image format (BITMAP, DIB).
   ・You can now enlarge/reduce the image format (BITMAP, DIB).
   ・Hold down the Ctrl key and use the mouse wheel or press Ctrl + ↑↓ to zoom.
   ・Binaries are no longer divided into Japanese and English versions.
   ・Changed saving settings in the area of each user.
   ・For Windows 10 "C:\Users\(username)\AppData\Local\CLCL"
   * Automatic transition on first run

・Version 2.0.2 -> Version 2.0.3
   ・Fixed a typo in the settings screen of the English version.

・Version 2.0.1 -> Version 2.0.2
   ・Supports Unicode for configuration file.
   After version 2.0.2 is launched, the configuration file will be Unicode encoded.
   The files before conversion are backed up with the file names "general.ini.back" and "clcl.ini.back".
   If you want to revert to an older version, use the above file.
   ・Changed the launch function from WinMain to wWinMain.

・Version 2.0.0 -> Version 2.0.1
   ・Imported patch code by K. Takata
   → Support for Unicode surrogate pairs
   → Retry processing when taskbar addition fails
   → Suppression of permanent double activation and suppression of double activation from another user
   ・Fixed an issue where the color of items disabled in the Behavior settings would sometimes disappear.
   ・Improved the icon on the taskbar when clipboard monitoring is stopped.

・Version 1.1.2 -> Version 2.0.0
   ・Unicode is supported. At the same time, old Windows are excluded from the object of operation.
   → The settings of the old version will be inherited, but formatting tools and plugins
     You must use a Unicode compatible version.
   ・Changed the file copy operation on successful save so that registered items do not disappear if the save process fails at the end of CLCL.
   ・Changed the design of icons on the taskbar.
   ・Changed the default action when clicking on the taskbar.
     → Given the work on the tablet, the left click on the tray icon changed it so that a menu appeared.
     
・Version 1.1.1 -> Version 1.1.2
   ・Fixed a bug that caused the tooltip background to not display correctly in 256-color environment.
   ・Optimized the way the menu is displayed.
   ・Optimized display of viewer text.

・Version 1.1.0 -> Version 1.1.1
   ・Improved performance when selecting a character position with the mouse when editing TEXT.
   ・Fixed an error that occurred when there is no history to save with a filter at the end.
   ・It is now possible to move items between history and registered items.
   ・Changed the thumbnail display method.
   ・The default timeout for copying and pasting has been changed to 100.
   ・Fixed the memory leak part.

・Version 1.0.9 -> Version 1.1.0
   ・If the menu hotkey is set to Ctrl+V, the menu will repeat.
   Fixed popup window.
   ・Enabled to specify the Windows key and spacebar as hotkeys for actions and tools.

・Version 1.0.8 -> Version 1.0.9
・Improved the display of confusion when canceling the confirmation message of the same format when creating a new file in the viewer.
   ・Fixed: Editing format content in the viewer unconditionally displayed the format being edited regardless of priority.
Fixed an issue where the status bar would not update when editing items in the viewer.
   ・Fixed an issue where the input position in Japanese sometimes shifted when editing TEXT.

・Version 1.0.7 -> Version 1.0.8
   ・Change INI file name (user.ini -> clcl.ini)
   Automatically rename files on startup.
   ・The display and editing of the TEXT format has been changed from advanced editing control to our own.
   ・Improved the performance of the viewer when calling the tool from the viewer.
   ・Enhanced binary display function.
   ·other

・Version 1.0.6 -> Version 1.0.7
   ・When an item is selected while pressing the Shift key in the menu, it is only sent to the clipboard without pasting.
   ・Added command line options.
   ・Fixed an issue where keys could not be sent to some windows.
   ・Increased the default list operation setting in the Options Viewer.

・Version 1.0.5 -> Version 1.0.6
   ・Make it possible to copy items in the operation settings.
   ・Changed the display range of the history display number in the operation settings.
   ・Fine adjustment of the options screen.

・Version 1.0.4 -> Version 1.0.5
   ・Hotkeys can now be assigned to registered items.
   ・Show hotkeys in the menu.
   ・Changed to not correct the position of the viewer on startup.
   ・Force save position and size when closing the viewer.
   ・0x7F was not displayed in the character display part of the binary code display.
   ・The file can now be opened even if it is locked.

・Version 1.0.3 -> Version 1.0.4
   ・When a file is in D&D status on the operation setting screen, it can be automatically registered as an external application.

・Version 1.0.2 -> Version 1.0.3
   ・Fixed an issue where the history was not saved correctly when the OS was closed in Windows XP.

・Version 1.0.1 -> Version 1.0.2
   ・Improved the memory release time related to the menu.
   ・Changed the use of the system icon for the folder icon.

・Version 1.0.0 -> Version 1.0.1
   ・Added customization items for each window.
   ・Fixed the issue that the text was not redrawn after changing the font depending on the environment.
   ・Fixed an issue where pasting is not possible with some programs.
   ・Fixed an issue that caused all windows to be targeted when specifying only one of window name and class name in window settings and key setting.

・Version 0.2.0 -> Version 1.0.0
   ・Rebuild

   No data or settings will be transferred.

   If you want to migrate registered items from version 0.2.0 to version 1.0.0, run both
   Send the version 0.2.0 registration item to the clipboard and add it to the version 1.0.0 history.
   And please register in the Ver 1.0.0 registration item from the story added in Ver 1.0.0.

   Tools that support version 0.2.0 can also be used with version 1.0.0. (Some restrictions apply)

--

The author is not responsible for any damage caused by this program.
It is highly recommended that you back up your important files.

Please send bug reports, requests and questions to nakka@nakka.com.

Copyright (C) 1996-2024 by Ohno Tomoaki. All rights reserved.
   https://www.nakka.com/

2024/1/29 