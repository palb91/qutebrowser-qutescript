=======================
Qutebrowser Userscripts
=======================

    :Author:      palb91
    :Licence:     MIT
    :Description: *Personal Qutebrowser userscripts*
    :Languages:   Python, Bash

cycle-owa
=========

::

    Cycle through user folders in office365.

    arguments:
        next    cycle from top to bottom (default)
        prev    cycle from bottom to top

    binding exemple:
        :bind « spawn -u cycle_owa
        :bind « spawn -u cycle_owa next
        :bind » spawn -u cycle_owa prev


wl-paste
========

Can be use as standalone or as userscript.

:Dependencies: - wtype;
               - bemenu;
               - wl-clipboard.

::

    Type or copy `pass` passwords in Wayland windows. Can be used as a
    qutebrowser userscript.

    Usage:
        wl-pass
        wl-pass type [-q] <user|pass|both> [URL]
        wl-pass copy <user|pass>      [URL]
        wl-pass help

    Command:
        type        Type the requested argument using wtype.
        copy        Copy the requested argument using wl-copy.
        help        Print this help.
        NONE        bemenu will be invoked to know what to do.

    Arguments:
        user        "username: user" in the pass file.
        pass        First line in the pass file.
        both        Type only, will output "username<Tab>password".
        NONE        bemeny will be invoked to know the target
        URL         wl-pass will try to find a matching result in
                    the password-store (and invoke bemenu when there
                    is more than one result).

    As qutebrowser userscript:
        Copy the script in: ~/.local/share/qutebrowser/userscripts
        Then map in ~/.config/qutebrowser/config.py, example:

            :bind('<Alt-u>', 'spawn -u -- wl-pass type user')
            :bind('<Alt-p>', 'spawn -u -- wl-pass type pass')
            :bind('<Alt-l>', 'spawn -u -- wl-pass type both')
            :bind('<Alt-u>', 'spawn -u -- wl-pass type user', mode='insert')
            :bind('<Alt-p>', 'spawn -u -- wl-pass type pass', mode='insert')
            :bind('<Alt-l>', 'spawn -u -- wl-pass type both', mode='insert')
