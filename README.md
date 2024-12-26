# Qucoostom keyboard layouts

(RU) Клавиатурные раскладки Куку́стэм

2024, by slavach@github

This software comes with absolutely no warranty. It can damage your life.  
The layouts are useful for me. Could be useful for you.  
Write me if you wish. Bugreports are welcome.  

## Description, Installation and Usage

### Symbols /usr/share/X11/xkb/symbols/qq

English and Russian `XKB symbols` for ugly cropped `61 keys keyboards`.

The layouts are hardcoded with `typo(base)` for 3-rd and 4-th levels. In order to use XKB options instead, you can comment out the includes `include "typo(base)"`.

K61 mappings is not the option but the feature of this symbols.

This symbols set also conntains the mix of Younger and Elder FUTHARK runes.

Look into `./symbols/qq` for the additional info, like the "pictures" of layouts.

#### How to install qq

1, Backup /usr/share/X11/xkb/symbols/qq if you have it.  
2, Copy the ./symbols/qq to /usr/share/X11/xkb/symbols/  

You can use the symbols with `setxkbmap` command.

    $ setxkbmap -layout qq,qq,qq -variant typo-us-k61,typo-ru-k61,mfuthark # ...

### XML Descriptions

In order to select the layouts in desktop environments, add the descriptions to XML rules. The XML descriptions are in the file `base.qq.inc.xml`.

To add the XML descriptions, cd to `/usr/share/X11/xkb/rules`, and:

1, Backup `base.xml` and `evdev.xml`.  
2, Insert `./rules/base.qq.inc.xml` into `base.xml` to the latest position inside the `layoutList`, right before the closing tag.  
`XPath: /xkbConfigRegistry/layoutList/layout[last]`  
3, Copy `base.xml` to `evdev.xml`.

PS. `setxkbmap` does not use the XML descriptions.

### Layouts Names in a Desktop Environment

1, English Qucoostom (US, Typo, K61) (Resides in the English Language)  
2, Russian Qucoostom (RU, Typo, K61) (Resides in the Russian Language)  
3, Younger and Elder Futhark Qucoostom (Resides in the English Language)  

### Text Descriptions

To add the text descriptions, cd to `/usr/share/X11/xkb/rules`, and:

1, Backup `base.lst` and `evdev.lst`.  
2, Add to the `! layout` list:  

    qq English Qucoostom (US)

3, Add to the `! variant` list:

    typo-us-k61 qq: English Qucoostom (US, Typo, K61)
    typo-ru-k61 qq: Russian Qucoostom (RU, Typo, K61)
    mfuthark qq: Younger and Elder Futhark Qucoostom

4, Copy `base.lst` to `evdev.lst`.

PS. Actually do not know what the commands are using `base.lst`, `evdev.lst`.

### Levels

    +-----+  1. No modifiers.
    | 2 4 |  2. Shift while pressed.
    | 1 3 |  3. ISO_Level3_Shift while pressed.
    +-----+  4. ISO_Level3_Shift+Shift while pressed.

