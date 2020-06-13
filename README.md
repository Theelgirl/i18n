# i18n
A translation system for Discord bots.

This is only supported on Linux/MacOS systems.

You must import the `i18n.py` file everywhere you need access to `_()`, even
if you dont use the `i18n.py` file.

You must import the `i18n.py` file at least once in order to let the
translation system work.

To generate a translation, run `./generate_po <language_name>`.
This will create a new folder for your translations, and search through
all of your files for translation markers (default: `_()`).

Once you fill in the translations, run `./generate_mo`, and the script will
compile all of the .PO files. **You must run this in order to get translations
working.**

## Common errors

#### FileNotFoundError: [Errno 2] No such file or directory: './locale/LANGUAGE/LC_MESSAGES/bot.po'
This means the script failed to find any translation markers. Remember to wrap
any string you want to translate with `_()`. E.g. `translated = _("Hello, world!")`.

#### msgcat: error while opening "./locale/LANGUAGE/LC_MESSAGES/bot.po.bak" for reading: No such file or directory
This isn't a real error, this just means that there was no backup file.

`msgcat` will attempt to merge all translations if possible. If this error appears,
it's like either your backup got deleted, or this is your first time running the script.

#### FileExistsError: [WinError 183] Cannot create a file when that file already exists: './locale/LANGUAGE/LC_MESSAGES/bot.po.cat' -> './locale/LANGUAGE/LC_MESSAGES/bot.po'
Again, this is not supported on windows.

## Footnote
The `i18n.py` file originated from [Emote Collector](https://github.com/EmoteBot/EmoteCollector/blob/master/emote_collector/utils/i18n.py), and I have been granted permission to use this file
for this repository.
