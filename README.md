interSubs
=========

v. 1.20

Interactive subtitles for `mpv`, that was made to help study languages. Easily tweaked and customizable.

- https://dict.cc/, https://pons.com/, http://reverso.net/, https://redensarten-index.de/ or Google for single words.
- https://www.deepl.com/translator for whole sentences.
- http://linguee.com/ redirecting to browser by click.
- https://forvo.com/, https://pons.com/ or Google for pronouncing single words.
- Can use multiple dictionaries simultaneously. 
-
- Doesn't work with DVD (picture based) subtitles, only the text-based ones.
- To convert picture based subtitles into *.srt - https://github.com/oltodosel/extract_n_convert_dvd_bd_subtitles
-
- Can colorize nouns by gender; German only with given dictionary.
- Works with right-to-left writing.
- Autodetects Hebrew and switches to r2l.
- Reassigning buttons' functions in config.
- Can extend time of subs showing; for slow readers

```
    00:02:23,046 --> 00:02:25,990
    bla bla
    00:02:28,020 --> 00:02:33,084
    waka waka
    
    00:02:23,046 --> 00:02:28,020
    bla bla
    00:02:28,020 --> 00:02:33,084
    waka waka
```

![ezgif com-video-to-gif](https://cloud.githubusercontent.com/assets/10230453/22852882/683b508e-f04f-11e6-87d0-7477164a1709.gif)

Requirements
------------
   - mpv 0.25 (I don't know if it will work with mpv front-ends.)
   - Python 3
   - numpy (pip)
   - beautifulsoup4 (pip)
   - Tcl/Tk 8.6.6
   - Lua
   - pkill
   - xdotool (for hiding subtitles when minimizing mpv or switching window) 
   - optional: chromium (for external translation, other browser can be specified)
   - optional: wget (for listening to pronunciation)

Installation
------------
```
mv interSubs.py interSubs.lua interSubs.conf.py ~/.config/mpv/scripts/;
mv interSubs.delexicon.txt ~/.config/mpv/scripts/; # only for German nouns colorization
# Edit configuration file interSubs.conf.py
# For Mac also edit configuration at interSubs.lua
# For Windows - port it yourself.
```

Usage
-----
- Start video with mpv & select subtitles.
- Press F5 to start/stop interSubs.
- Point cursor over the word to get popup with translation.

buttons bellow may be reassigned
-----
- Click on the word to look it up on another translator in the browser.
- Right-click on the word to hear its pronunciation.
- Wheel - scroll through transitions in popup.
- Wheel+Ctrl - resize subtitles.
- Wheel+Shift - change subtitles' vertical position.
- Wheel-click - cycle through auto_pause options.
- Wheel-click-left/right - +/- auto_pause_min_words. (fancy mouses)
- Wheel-back - translate whole sentence.

Important
-----
- By default works only in fullscreen.
- May have issues working in a multi-monitor system.


Changelog
-----
- 1.14 - Added simultaneous use of multiple dictionaries. When using more than one - scrolling is infinite.
- 1.15 - Added multi-threaded retrieval when using more than one dictionary. Works only with `save_translations = 1`
- 1.16 - Added waiting cursor. Minor errors correction.
- 1.17 - Minor errors correction.
- 1.18 - Added redensarten-index.de support (German idioms).
- 1.19 - Added option to reassign buttons.
         Added support for deepl.com; to translate whole sentences. Supported languages: de, en, fr, es, it, nl, pl.
         Version are not back compatible with previous config.
- 1.20 - Added function to save words to a file. Boundable to a mouse-button.
