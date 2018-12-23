# Qstit
Qstit is a QT based Free Software for live projection and manipulation of electronic subtitles (also called "surtitles", "supertitles", "soft-titles"...). **Qstit** is composed of a **display** (the textframe with titles to be projected), a **control bar** (with the buttons) and a **grid** (the list of titles), all of which can be moved around on the **fullscreen background** depending on the desired set-up.

This project is distributed under GNU General Public License, version 3 or later --- see the file COPYING for details. This project was originally developed by Nova Cinema, Brussels - [subtitles.nova-cinema.org](http://subtitles.nova-cinema.org). This fork is currently maintained by Naatak Org - [naatak.com](https://naatak.com). Icons used in this project are provided by Nova & Axialis Team (with some modifications) - [www.axialis.com/free/icons](https://www.axialis.com/free/icons)

## HowTo
When a projector is plugged to the computer, it is considered as a second monitor. If the computer is set to have the same image on both screens, you will need to hide the controls from the public, the title display is the only part they need to see. Use a cover (a piece of cardboard in front of the projector can do the trick), aim the projector to hit the screen with only the top part of the image (where the display will be placed), or select only this part of the signal using a video-mixer. You can also configure your computer display to have two separate screens. In that case you need to have the controls on your screen and only the display and the fullscreen background on the projector. This can already work but it can be a bit tricky as **Qstit** doesn't fully support the detection of multiple screens yet.

### Supported file formats
**Qstit** can read simple text (.txt) with up to four lines per title. **Qstit** provides support for UTF-8 encoding which makes it possible to display all sorts of characters in all languages.

For `.txt` file type the structure (detailed below) needs to be respected carefully otherwise **Qstit** won't be able to open them correctly. If errors are found when opening the file, a message is displayed. The errors encountered are listed in the 'File info' window and also saved in a log file in the same folder as the title file (the **log file** is also created if titles are flagged or if modifications have been made using the 'Edit' functionality).

`.txt` can include the following HTML tags to change the style of the text in between them:
```
<i> _italic_ </i>
```
```
<b> **bold** </b>
```
```
<u> underline </u>
```

A tag can start on one line and end on another, wherever in the file. Whole sections can easily be turned into italic, for instance. The tags themselves are not displayed but appear in the grid. Everything written between an opening (<) and a closing (>) bracket (or a line break) will be considered as a tag and won't be displayed. An entire line between brackets will still appear in the grid like a normal title but won't appear on the display. Brackets can thus be used to put comments and cues in the file.

#### Text (.txt) files

Rules
- One line in the file = one row in the grid = one title.
- One title can be composed of several lines (up to four, usually two), they are separated by a backslash (\).
- Different titles can be composed of different numbers of lines.
· Titles are only separated by a line break.
- **Qstit** automatically creates "empty" lines between titles so that nothing is displayed between two titles when there are no dialogues. There is no need to have empty lines in the file, they would be considered as one title, even if there isn't any text. There would therefore be three consecutive "empty lines" when browsing through the file.

##### Format

```
Title 1 Line 1\Title 1 Line 2
Title 2 Line 1
Title 3, Line 1\Title 3, Line 2\Title 3, Line 3
Title 4, Line 1\Title 4, Line 2
...
```

Example: Shows the first title is italized, subsequently the second title is bolder but has 2 more subsequent lines.

```
<i>Welcome to Naatak's Gujarati Mela 2018</i>
<b>FITTING ROOMS</b>\ Author: Susan Cinoman,Translation:Sameer Pandya\ Director: Natraj Kumar
MADHURI: Hmm... If I buy this, my husband will kill me.
LEENA: You are kidding. Right?
MADHURI: Ofcourse I don't mean that literally but he will not like it.
LEENA: Well, who cares about that! It is not like he makes you happy anyways.
MADHURI: But can anyone really make anyone else happy?
LEENA: What do you mean?
MADHURI: One needs to keep oneself happy. Right?
LEENA: Good then, you found a good excuse to buy this dress.
...
```

### Controls
**Qstit** can be controlled with the mouse and / or keyboard. The controls and keyboard shortcuts are detailed below.
It is possible to fully control **Qstit** with just a numeric keypad (or "numpad"). An external keypad can therefore be used as a remote control.

#### Menu

![](src/Imag/QSTit_sett_enab.png) Settings

Show 'Settings' window

\[Ctrl+S\]

![](src/Imag/QSTit_file.png) Open

Open title file (Supported formats: .txt)

\[Ctrl+O\]

![](src/Imag/QSTit_help_enab.png) Help

Show this window

\[F1\]

![](src/Imag/QSTit_exit.png) Quit

Quit the program

\[Ctrl+Q\]

#### Titles control

![](src/Imag/QSTit_upup.png)

Previous title / empty line

\[↑\] or \[Numpad 8\]

![](src/Imag/QSTit_down.png)

Next title / empty line With .txt files, also works with:

\[↓\] or \[Numpad 2\]
\[Space bar\] or \[Numpad 0\]

![](src/Imag/QSTit_play.png)

Start / Pause timer

\[Space bar\] or \[Numpad 0\]

#### Display control

![](src/Imag/QSTit_roll_open.png) / ![](src/Imag/QSTit_roll_clos.png)

Hide / Show title display
(When on pause, restarting makes the display appear)

\[X\] or \[Numpad .\]

Move display up

\[Page Up\] or \[Numpad 9\]

Move display down

\[Page Down\] or \[Numpad 3\]

Move display left

\[Home\] or \[Numpad 7\]

Move display right

\[End\] or \[Numpad 1\]

→ use \[Shift\] for faster movements

It is also possible to move the display with the mouse

\[Click and drag\]

#### Grid

![](src/Imag/QSTit_info_enab.png) File info

Show 'File info' window

\[Ctrl+I\]

![](src/Imag/QSTit_save_enab.png) Save as...

Save modified file as...

![](src/Imag/QSTit_edit_enab.png) Edit

Edit selected text / timecode in the grid
(Edits are indicated in the grid and listed in the log file)

\[Ctrl+E\]

![](src/Imag/QSTit_undo_enab.png) Undo

Undo changes (in reverse chronology)

\[Ctrl+Z\]

![](src/Imag/QSTit_goto_enab.png) Go to...

Go to a chosen title

\[Ctrl+G\]

![](src/Imag/QSTit_find_enab.png) Find...

Find text in the file

\[Ctrl+F\]

![](src/Imag/QSTit_clea.png) Clear

Clear display and reset file at beginning

\[Ctrl+C\]

![](src/Imag/QSTit_link_none.png) Bind/Unbind

(Un)bind menu bar and grid for custom positioning

![](src/Imag/QSTit_flag.png) (Leftmost cell)

Flag current row to indicate a cue, a mistake, etc.
(Flags are saved in the log file)

\[!\] or \[Numpad /\]

#### Advanced Settings
Various display and control settings can be adjusted in the 'Settings' window. The display can be adapted line per line or all lines together. Note that you can make a line "**invisible**" using the advanced settings. The full text will still appear in the grid for your control but it won't be displayed. It can be useful if the titles are one language on Line 1 and another on Line 2, for instance, and you only need to project one of the two but want to keep the translation in the file.

Settings can be saved for later use with the current file or as general settings for all files. **Settings saved for a specific file** will be named like it (with a .cfg extension) and placed in the same folder as the subtitle file. **General settings** are saved in a file named "qstit.cfg" which will be created in your "home" or "user" folder, depending on your system (in a ".qstit" subfolder). There are also **default settings** built in the program that can be restored to replace your configurations, if needed. If you don't need the settings anymore, you can just delete the .cfg files.

When opening a new file, you can choose which settings to use. Once a file is opened, you can always load preset settings using the designated functions in the 'Save / Load' tab. It is recommended to test your settings while displaying one of the the widest lines, which are listed in the title bar and in the 'File info' window.

