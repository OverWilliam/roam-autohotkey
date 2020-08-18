# roam-autohotkey
A series of scripts for automating Roam Research tasks on Windows.


<a href='https://ko-fi.com/R6R622EYH' target='_blank'><img height='30' style='border:0px;height:36px;' src='https://cdn.ko-fi.com/cdn/kofi5.png?v=2' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

# Table of Contents

* [Download AutoHotkey](#download-autohotkey)
* Script Descriptions
    * [copy-to-roam](#copy-to-roam)
    * [youtube-timestamp](#youtube-timestamp)
    * [title-case-and-header](#title-case-and-header)

# Download AutoHotkey
To run the scripts in this repo, you'll need to have [AutoHotkey](https://www.autohotkey.com/). See the [AutoHotkey Beginner Tutorial](https://www.autohotkey.com/docs/Tutorial.htm) for detailed steps on how to install and an overview of some basic concepts.

# [copy-to-roam](https://github.com/OverWilliam/roam-autohotkey/blob/master/copy-to-roam.ahk)

This extremely simple script copies highlighted text, sends the Windows Alt+Tab keyboard shortcut to switch to the previous window, and then pastes whatever is in the clipboard:

![gif example of copy-to-roam](https://github.com/CFiggers/roam-autohotkey/blob/master/gifs/copy-to-roam-example2.gif)

Will work OS-wide, not just for Roam, but is not smart enough to select a specific window. It just switches to the previous window from wherever the shortcut is triggered. Currently keyed to Alt + V (configurable by changing the first line in the script; see comment).

# [youtube-timestamp](https://github.com/CFiggers/roam-autohotkey/blob/master/youtube-timestamp.ahk)

Grabs the Youtube timestamp of a currently-playing video and puts it in the clipboard ready to paste somewhere else (such as Roam). Does not pause the video and works with currently-running videos. Currently keyed to Alt + O (configurable by changing the first line in the script):

![gif example of youtube-timestamp](https://github.com/CFiggers/roam-autohotkey/blob/master/gifs/youtube-timestamp-example.gif)

Works by executing the following steps:
* Select the entire current window (Ctrl+A)
* Copy the current selection (Ctrl+C)
* Run a RegEx on the current Clipboard contents to extract the current timestamp
* Replace the Clipboard contents with the extracted timestamp
* Automatically click the mouse at a pre-set position in the current window to de-select the current window
* Return mouse to starting position

Could easily be extended to also switch from the current window (e.g. in Roam) to the window containing Youtube, grab the timestamp, automatically switch back, and automatically paste the grabbed timestamp for more Eloquent-like functionality.

# [title-case-and-header](https://github.com/CFiggers/roam-autohotkey/blob/master/title-case-and-header.ahk)

Corrects all punctuation to Title Case (ignoring common words per [APA Style Guidelines](https://apastyle.apa.org/style-grammar-guidelines/capitalization/title-case) (easy to update if you prefer a different list), and also triggers Ctrl+Alt+{1,2,3} to create header level in Roam:

![gif example of title-case-and-header](https://github.com/CFiggers/roam-autohotkey/blob/master/gifs/title-case-and-header-example.gif)

Three different keyboard shortcuts in use:
* Alt+B for 1st Level Header
* Alt+N for 2nd Level Header
* Alt+M for 3rd Level Header

All three correct capitalization. Must be in active edit mode on a block to work properly (otherwise, selects the entire Roam page and may appear to delete it--be careful and remember to Ctrl+Z if needed!).
