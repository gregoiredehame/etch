# Etch roadmap

Where Etch goes from 0.3, in the order that matters most. Each step is usable on its own.

## 0.1 (built)

### Drawing

- **Glass on every screen:** draw, or point through the ink, and switch with Ctrl+Alt+D or Esc.
- **Tools:**
  - a pen that follows a stylus's pressure;
  - a highlighter;
  - an eraser that takes whole marks;
  - lines, arrows, rectangles and ellipses, with Shift for straight, square and round;
  - text.
- **Undo and redo:** one history across the screens. One eraser stroke is one undo.
- **Boards:** a whiteboard and a blackboard, each with its own ink.
- **Fading ink:** each mark goes away on its own after a few seconds.
- **The glass leaves:** when nothing is drawn and no effect is on, the glass goes away entirely, so a game stays full
  screen.

### Showing what happens

- **Keys typed:**
  - two modes, shortcuts only or everything typed;
  - read through the layout of the window typed in, so AZERTY, AltGr and dead keys come out right;
  - the keyboard is watched only while the keys are shown, and never held back.
- **Pointer:** a halo, and rings on clicks.

### Capture

- **Screenshots** of a screen or a rectangle, saved and copied, the toolbar left out.
- **Recordings:** MP4 with a countdown and a pause, the graphics card's encoder first.

### The toolbar and the rest

- **Toolbar:**
  - upright or lying, folded by a double click on its grip;
  - it never takes the focus and stays out of captures.
- **Shortcuts** that work from any application.
- **Settings.**
- **One Etch per user,** with an icon in the notification area.

## 0.2 (built)

### Brushes

- **Seven brushes:** pen, marker, pencil, calligraphy, neon, highlighter and laser.
- **Each brush keeps its own settings:**
  - size, opacity and smoothing;
  - what the pressure changes: the width, the darkness, or both.
- **Pressure:**
  - a curve: soft, linear or firm;
  - a pad in the settings to try a brush, with the stylus's pressure shown.
- **Laser:** a glowing trail that fades within a moment and never goes on the sheet.

### Colour

- **A colour chooser** beside the toolbar:
  - shades and hue;
  - the colour's code;
  - the brush's opacity;
  - the palette, where a right click keeps a colour;
  - the colours used last.
- **An eyedropper** that takes a colour from anywhere on the screens.

### Screenshots

- **The screens freeze first.** A menu or a tooltip stays as it was.
- **What a click takes:**
  - a click takes the window under the pointer, which is outlined;
  - a drag takes a rectangle;
  - Enter takes the screen.
- **A magnifier** shows the pixels under the pointer, their colour and their place.
- **Every screen at once,** or a delay of 3, 5 or 10 seconds.
- **Saving:** PNG or JPG, the ink kept or left out.
- **The card after a screenshot:**
  - copy, save as, pin, open the folder, delete;
  - a pinned screenshot stays above everything, and the wheel zooms it.

### Recordings

- **Windows Graphics Capture:**
  - up to 60 frames a second, measured at 59 on a whole 1920x1200 screen;
  - the pointer drawn by Windows;
  - a still screen costs nothing.
- **Sound:**
  - the computer's sound, and the microphone when asked, mixed in AAC;
  - in step with the picture: 2.04 s of sound for 2.03 s of picture.
- **A frame around a rectangle being recorded,** never in the video.

### Faster

- **A stroke being drawn** is painted one new segment at a time. On a 2000-point stroke, a move costs 1.3 ms instead
  of 31.6 ms in 0.1.
- **The eraser** tests the points in numpy.
- **A long stroke** paints only its part inside the area repainted.

## 0.3 (built)

### One capture for everything

- **The same gesture for a picture, a GIF and a video:** the screens freeze, a click takes a window, a drag a
  rectangle, Enter the screen. A bar at the top (or Tab, 1 2 3) says what is taken.
- **A GIF records at once,** without sound, and stops on its own at its longest (15 s at first). It is made in two
  passes through FFmpeg's filters, one palette for the whole clip, so its colours never flicker; 2 s of a moving
  square at 15 frames a second take 0.2 s and 44 KB.
- **A small bar beside a recording:** the time (and the longest a GIF may be), pause, stop, give up. Never in the
  recording, never takes the focus.

### What follows a capture

- **A card for each kind,** stacked in the corner: a GIF plays in it, a video shows its first picture and its length.
- **Dragged out of the card, a capture goes into any application** as its file, always copied.
- **A video's card makes a GIF of it.**
- **Delete goes to the Recycle Bin.**

### Captures, the history

- **Every capture kept** with the window and the application it was taken from (the name the program gives itself).
- **A window to find them again:** search by window, application, date or kind; filter by kind; drag several out at
  once; open, copy, show in the folder, pin, make a GIF, delete.

## 1. Next

- **A test with real devices.**
  - The microphone: it is built and off by default, never opened in the checks.
  - A pen tablet's pressure through Windows Ink: the checks give the pressures themselves.
- **Start with Windows,** as an option off by default.
- **The microphone's level** shown in the record menu, so a silent microphone is seen before recording.

## 2. A product

- **An installer and updates** like Seam's: publish.py, the release on GitHub, latest.json, the update check in the
  settings.
- **The interface in the eight languages,** translated at publish time.
- **A signed executable,** so SmartScreen does not warn.

## 3. More ink

- **Select, move, resize and delete marks,** with a lasso.
- **Save and open a drawing.**
- **Export the ink alone** as a transparent PNG.
- **Presentation tools:**
  - a spotlight that darkens everything but a circle around the pointer;
  - a magnifier that follows the pointer.
- **Stamps:** numbers that count up (1, 2, 3...), ticks and crosses.
- **Line styles:** dashed lines, and filled shapes.
- **Shape recognition:** a rough circle drawn by hand becomes an ellipse.
- **Brush presets:** a brush with its colour and size kept under a name, a click away on the toolbar.

## 4. Captures

- **A link to share:** a capture sent to a server of one's own (or a shared folder) and its address copied, so a chat
  gets a link rather than a file.
- **The last seconds:** the screen kept a few seconds back while a game or a session runs, saved on a shortcut, for
  what happened before it was asked for.
- **Annotate a capture** before saving it: arrows, a blur over a password.
- **Trim a recording's ends** after it stops, before its GIF.
- **A GIF's size before it is made,** with the frame rate and the width to choose in its card.
- **The camera in a corner of the recording.**
- **Mouse buttons and the wheel shown with the keys,** for example "Ctrl + click".

## 5. Other systems

macOS and Linux. The glass, the toolbar and the ink are Qt already. What changes is native.py and the capture: going
through the mouse, staying out of captures, the global shortcuts, the keyboard watch and the screen capture.
