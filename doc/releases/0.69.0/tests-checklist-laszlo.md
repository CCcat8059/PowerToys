## Functional tests

 Regressions:
 - [ ] https://github.com/microsoft/PowerToys/issues/1414#issuecomment-593529038
 - [ ] https://github.com/microsoft/PowerToys/issues/1524


## Color Picker
* Enable the Color Picker in settings and ensure that the hotkey brings up Color Picker
  - [ ] when PowerToys is running unelevated on start-up
  - [ ] when PowerToys is running as admin on start-up
  - [ ] when PowerToys is restarted as admin, by clicking the restart as admin button in the settings
- [ ] Change `Activate Color Picker shortcut` and check the new shortcut is working
- [ ] Try all three `Activation behavior`s(`Color Picker with editor mode enabled`, `Editor`, `Color Picker only`)
- [ ] Change `Color format for clipboard` and check if the correct format is copied from the Color picker
- [ ] Try to copy color formats to the clipboard from the Editor
- [ ] Check `Show color name` and verify if color name is shown in the Color picker
- [ ] Enable one new format, disable one existing format, reorder enabled formats and check if settings are populated to the Editor
- [ ] Select a color from the history in the Editor
- [ ] Remove color from the history in the Editor
- [ ] Open the Color Picker from the Editor
- [ ] Open Adjust color from the Editor
- [ ] Check Color Picker logs for errors

## Image Resizer
- [ ] Disable the Image Resizer and check that `Resize images` is absent in the context menu
- [ ] Enable the Image Resizer and check that `Resize images` is present in the context menu. (On Win11) Check if both old context menu and Win11 tier1 context menu items are present when module is enabled.
- [ ] Remove one image size and add a custom image size. Open the Image Resize window from the context menu and verify that changes are populated
- [ ] Resize one image
- [ ] Resize multiple images
- [ ] Open the image resizer to resize a `.gif` file and verify the "Gif files with animations may not be correctly resized." warning appears.

- [ ] Resize images with `Fill` option
- [ ] Resize images with `Fit` option
- [ ] Resize images with `Stretch` option

- [ ] Resize images using dimension: Centimeters
- [ ] Resize images using dimension: Inches
- [ ] Resize images using dimension: Percents
- [ ] Resize images using dimension: Pixels

- [ ] Change `Filename format` to `%1 - %2 - %3 - %4 - %5 - %6` and check if the new format is applied to resized images
- [ ] Check `Use original date modified` and verify that modified date is not changed for resized images. Take into account that `Resize the original pictures(don't create copy)` should be selected
- [ ] Check `Make pictures smaller but not larger` and verify that smaller pictures are not resized
- [ ] Check `Resize the original pictures (don't create copies)` and verify that the original picture is resized and a copy is not created
- [ ] Uncheck `Ignore the orientation of pictures` and verify that swapped width and height will actually resize a picture if the width is not equal to the height

## Keyboard Manager

UI Validation:

  - [ ] In Remap keys, add and remove rows to validate those buttons. While the blank rows are present, pressing the OK button should result in a warning dialog that some mappings are invalid.
  - [ ] Using only the Type buttons, for both the remap windows, try adding keys/shortcuts in all the columns. The right-side column in both windows should accept both keys and shortcuts, while the left-side column will accept only keys or only shortcuts for Remap keys and Remap shortcuts respectively. Validate that the Hold Enter and Esc accessibility features work as expected.
  - [ ] Using the drop downs try to add key to key, key to shortcut, shortcut to key and shortcut to shortcut remapping and ensure that you are able to select remapping both by using mouse and by keyboard navigation.
  - [ ] Validate that remapping can be saved by pressing the OK button and re-opening the windows loads existing remapping.

Remapping Validation:

For all the remapping below, try pressing and releasing the remapped key/shortcut and pressing and holding it. Try different behaviors like releasing the modifier key before the action key and vice versa.
  - [ ] Test key to key remapping
    - A->B
    - Ctrl->A
    - A->Ctrl
    - Win->B (make sure Start menu doesn't appear accidentally)
    - B->Win (make sure Start menu doesn't appear accidentally)
    - A->Disable
    - Win->Disable
  - [ ] Test key to shortcut remapping
    - A->Ctrl+V
    - B->Win+A
  - [ ] Test shortcut to shortcut remapping
    - Ctrl+A->Ctrl+V
    - Win+A->Ctrl+V
    - Ctrl+V->Win+A
    - Win+A->Win+F
  - [ ] Test shortcut to key remapping
    - Ctrl+A->B
    - Ctrl+A->Win
    - Win+A->B
  * Test app-specific remaps
    - [ ] Similar remaps to above with Edge (entered as `msedge`), VSCode (entered as `code`) and cmd. For cmd try admin and non-admin (requires PT to run as admin)
    - [ ] Try some cases where focus is lost due to the shortcut. Example remapping to Alt+Tab or Alt+F4
  - [ ] Test switching between remapping while holding down modifiers - Eg. Ctrl+D->Ctrl+A and Ctrl+E->Ctrl+V, hold Ctrl and press D followed by E. Should select all and paste over it in a text editor. Similar steps for Windows key shortcuts.

## PowerRename
- [ ] Check if disable and enable of the module works. (On Win11) Check if both old context menu and Win11 tier1 context menu items are present when module is enabled.
- [ ] Check that with the `Show icon on context menu` icon is shown and vice versa.
- [ ] Check if `Appear only in extended context menu` works.
- [ ] Enable/disable autocomplete.
- [ ] Enable/disable `Show values from last use`.
* Select several files and folders and check PowerRename options:
    - [ ] Make Uppercase/Lowercase/Titlecase (could be selected only one at the time)
    - [ ] Exclude Folders/Files/Subfolder Items (could be selected several)
    - [ ] Item Name/Extension Only (one at the time)
    - [ ] Enumerate Items
    - [ ] Case Sensitive
    - [ ] Match All Occurrences. If checked, all matches of text in the `Search` field will be replaced with the Replace text. Otherwise, only the first instance of the `Search` for text in the file name will be replaced (left to right).
    * Use regular expressions
        - [ ] Search with an expression (e.g. `(.*).png`)
        - [ ] Replace with an expression (e.g. `foo_$1.png`)
        - [ ] Replace using file creation date and time (e.g. `$hh-$mm-$ss-$fff` `$DD_$MMMM_$YYYY`)
        - [ ] Turn on `Use Boost library` and test with Perl Regular Expression Syntax (e.g. `(?<=t)est`)
    * File list filters.
        - [ ] In the `preview` window uncheck some items to exclude them from renaming.
        - [ ] Click on the `Renamed` column to filter results.
        - [ ] Click on the `Original` column to cycle between checked and unchecked items.

## PowerToys Run

 * Enable PT Run in settings and ensure that the hotkey brings up PT Run
   - [ ] when PowerToys is running unelevated on start-up
   - [ ] when PowerToys is running as admin on start-up
   - [ ] when PowerToys is restarted as admin, by clicking the restart as admin button in settings.
 * Check that each of the plugins is working:
   - [ ] Program - launch a Win32 application
   - [ ] Program - launch a Win32 application as admin
   - [ ] Program - launch a packaged application
   - [ ] Calculator - ensure a mathematical input returns a correct response and is copied on enter.
   - [ ] Windows Search - open a file on the disk.
   - [ ] Windows Search - find a file and copy file path.
   - [ ] Windows Search - find a file and open containing folder.
   - [ ] Shell - execute a command. Enter the action keyword `>`, followed by the query, both with and without space (e.g. `> ping localhost`).
   - [ ] Folder - Search and open a sub-folder on entering the path.
   - [ ] Uri - launch a web page on entering the uri.
   - [ ] Window walker - Switch focus to a running window.
   - [ ] Service - start, stop, restart windows service. Enter the action keyword `!` to get the list of services.
   - [ ] Registry - navigate through the registry tree and open registry editor. Enter the action keyword `:` to get the root keys.
   - [ ] Registry - navigate through the registry tree and copy key path.
   - [ ] System - test `lock`.
   - [ ] System - test `empty recycle bin`.
   - [ ] System - test `shutdown`.

 - [ ] Disable PT Run and ensure that the hotkey doesn't bring up PT Run.

 - [ ] Test tab navigation.

 * Test Plugin Manager
   - [ ] Enable/disable plugins and verify changes are picked up by PT Run
   - [ ] Change `Direct activation phrase` and verify changes are picked up by PT Run
   - [ ] Change `Include in global result` and verify changes picked up by PT Run
   - [ ] Clear `Direct activation phrase` and uncheck `Include in global result`. Verify a warning message is shown.
   - [ ] Disable all plugins and verify the warning message is shown.

## Shortcut Guide
 * Run PowerToys as user:
   - [ ] Verify `Win + Shift + /` opens the guide
   - [ ] Change the hotkey to a different shortcut (e.g. `Win + /`) and verify it works
   - [ ] Set Shortcut Guide to start with a Windows key press and verify it works.
 * Restore the `Win + Shift + /` hotkey.
   - [ ] Open the guide and close it pressing `Esc`
   - [ ] Open the guide and close it pressing and releasing the `Win` key
 * With PowerToys running as a user, open an elevated app and keep it on foreground:
   - [ ] Verify `Win + Shift + /` opens the guide
   - [ ] Verify some of the shortcuts shown in the guide work and the guide is closed when pressed

## OOBE
 * Quit PowerToys
 * Delete %localappdata%\Microsoft\PowerToys
 - [ ] Start PowerToys and verify OOBE opens
 * Change version saved on `%localappdata%\Microsoft\PowerToys\last_version.txt`
 - [ ] Start PowerToys and verify OOBE opens in the "What's New" page
 * Visit each OOBE section and for each section:
   - [ ] open the Settings for that module
   - [ ] verify the Settings work as expected (toggle some controls on/off etc.)
   - [ ] close the Settings
   - [ ] if it's available, test the `Launch module name` button
 * Close OOBE
 - [ ] Open the Settings and from the General page open OOBE using the `Welcome to PowerToys` link

## Always on Top
 - [ ] Pin/unpin a window, verify it's topmost/not topmost.
 - [ ] Pin/unpin a window, verify the border appeared/disappeared.
 - [ ] Switch virtual desktop, verify border doesn't show up on another desktop.
 - [ ] Minimize and maximize pinned window, verify the border looks as usual.
 - [ ] Change border color and thickness.
 - [ ] Verify if sound is played according to the sound setting.
 - [ ] Exclude app, try to pin it.
 - [ ] Exclude already pinned app, verify it was unpinned.
 - [ ] Try to pin the app in the Game Mode.

### Screen Ruler
 * Enable Screen Ruler. Then:
   - [ ] Press the activation shortcut and verify the toolbar appears.
   - [ ] Press the activation shortcut again and verify the toolbar disappears.
   - [ ] Disable Screen Ruler and verify that the activation shortuct no longer activates the utility.
   - [ ] Enable Screen Ruler and press the activation shortcut and verify the toolbar appears.
   - [ ] Select the close button in the toolbar and verify it closes the utility.
 * With Screen Ruler enabled and activated:
   - [ ] Use the Bounds utility to measure a zone by dragging with left-click. Verify right click dismisses the utility and that the measurement was copied into the clipboard.
   - [ ] Use the Spacing utility to measure something and verify that left-click copies the measurement to the clipboard. Verify that right-click dismisses the utility.
   - [ ] Use the Horizontal Spacing utility to measure something and verify that left-click copies the measurement to the clipboard. Verify that right-click dismisses the utility.
   - [ ] Use the Vertical Spacing utility to measure something and verify that left-click copies the measurement to the clipboard. Verify that right-click dismisses the utility.
   - [ ] While using a Spacing utility, verify that using the mouse scroll wheel will adjust pixel color tolerance while measuring.
   - [ ] Open mspaint and draw 1px-thick straight line, also click with a pencil to draw a single pixel. In any Spacing mode, verify that one of line's dimension is 1, and pixel's dimensions are 1x1.
 * In a multi-monitor setup with different dpis on each monitor:
   - [ ] Verify that the utilities work well on each monitor, with continuous mode on and off.
   - [ ] Without any window opened and a solid color as your background, verify the horizontal spacing matches the monitor's pixel width.
   - [ ] Move your mouse back and forth around the edge of two monitors really quickly in each mode - verify nothing is broken.
   
 * Test the different settings and verify they are applied:
   - [ ] Activation shortcut
   - [ ] Continous mode
   - [ ] Per color channel edge detection
   - [ ] Pixel tolerance for edge detection
   - [ ] Draw feet on cross
   - [ ] Line color

### Quick Accent
 * Enable Quick Accent and open notepad. Then:
   - [ ] Press `a` and the left or right arrow and verify the accent menu appears and adds the accented letter you've selected. Use left and arrow keys to cycle through the options.
   - [ ] Press `a` and the space key and verify the accent menu appears and adds the accented letter you've selected. Use <kbd>Space</kbd> to navigate forward, <kbd>Space</kbd> + <kbd>Shift</kbd> to navigate backward.
   - [ ] Disable Quick Accent and verify you can no longer add accented characters through Quick Accent.
 * Test the different settings and verify they are applied:
   - [ ] Activation key
   - [ ] Language (for example, Currency has no accents for 'a' but has for 's')
   - [ ] Toolbar position (test every option, some had issues before)
   - [ ] Input delay
   - [ ] Exclude some apps. Verify that Quick Accent is not activated for them.
   - [ ] Sort characters by frequency.
   - [ ] Always start on the first character when using left/right arrows as activation method.

### Text Extractor
 * Enable Text Extractor. Then:
   - [ ] Press the activation shortcut and verify the overlay appears.
   - [ ] Press Escape and verify the overlay disappears.
   - [ ] Press the activation shortcut and verify the overlay appears.
   - [ ] Right-click and select Cancel. Verify the overlay disappears.
   - [ ] Disable Text Extractor and verify that the activation shortuct no longer activates the utility.
 * With Text Extractor enabled and activated:
   - [ ] Try to select text and verify it is copied to the clipboard.
   - [ ] Try to select a different OCR language by right-clicking and verify the change is applied.
 * In a multi-monitor setup with different dpis on each monitor:
   - [ ] Verify text is correctly captured on all monitors.
 * Test the different settings and verify they are applied:
   - [ ] Activation shortcut
   - [ ] OCR Language

### Registry Preview
 * Open Registry Editor, add new registry key with 1 string value and 1 binary value in e.g. HKLM/Software/Classes/PowerToysTest. Right click new registry key->export and export it to file.
 * Launch Registry Preview by right-clicking exported .reg file->'Preview'. Then:
   - [ ] Uncheck ReadOnly checkbox and edit file content. Ensure that visual try is being re-populated while typing. Save the file by pressing Save file button. Confirm that file is properly saved by pressing Edit file... button which will open file in Notepad. Try saving file using Save file as... button.
   - [ ] Edit file externaly (e.g. in Notepad) and save it there. Pres Reload from file button and ensure that file content and visual tree are reloaded and show new content.
   - [ ] Select some registry key with registry values in visual tree and ensure that registry values are shown properly in bottom-right area.
   - [ ] Try opening different registry file by pressing Open file button.
   - [ ] Delete newly created registry key from first step manually in Registry Editor, then try writing registry changes to registry by pressing Write to Registry button in Registry Preview. *Be careful what you are writing!* 
   
 * Open Registry Preview Settings. Then:
   - [ ] Disable Registry Preview and ensure that Preview context menu option for .reg files no longer appears.
   - [ ] Try to launch Registry Preview from it's OOBE page while Registry Preview is disabled and ensure that it does not start.
   - [ ] Enable Registry Preview again and ensure that Preview context menu option for .reg files appears and that it starts Registry Preview correctly. 
   - [ ] Try to launch Registry Preview from it's Settings page and ensure that it is launched properly.
   - [ ] Try to launch Registry Preview from it's OOBE page and ensure that it is launched properly.