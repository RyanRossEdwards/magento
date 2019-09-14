# Vim Notes
Simply because it's used so much...

![alt text][vimcheatsheet]

[vimcheatsheet]: https://github.com/rryanedwards/magento/raw/master/resources/vim-shortcuts-dark_2560x1600.png "Vim Cheat Sheet"

Think of Vim as **Verb + Noun** phrases designed for repeatability, for instance <kbd>d</kbd>+<kbd>w</kbd> represents delete + word. 

Use  <kbd>.</kbd> to repeat an action. 

Use  <kbd>u</kbd> to undo an action. 

## Verbs
### Basic

Key | Action
--- | ---
`d` | delete
`c` | change

## Nouns
### Text Objects

Keys | Literally | Description
--- | ---       | ---
`aw` | a word    | includes white space
`iw` | inner word| excludes white space
`as` | a sentence| includes white space
`is` | inner sentence | excludes white space
`i"` | inner double quote | excludes quotes
`i'` | inner single quote | "
`i(` | inner brackets | "
`it` | inner (html) tag | "
`ip` | inner paragraph | "

### Parameterised Text Objects
<kbd>f</kbd> + `character` (forward) or <kbd>F</kbd> + `character` (backwards)

<kbd>t</kbd> + `character` (forward) or <kbd>T</kbd> + `character` (backwards)

<kbd>/</kbd> + `word`

E.g. <kbd>d</kbd> + <kbd>2</kbd> + <kbd>/</kbd> + `to` will delete everything between cursor and the next next occurrence of `to`. 

## Tricks
### Relative Line Numbers
`:set nu rnu` `set number relativenumber`

`:set nonu nornu` for off, `:set nu! rnu!` for toggle

### Multi Lines
Very useful for commenting and indenting, use block visual iditor: <kbd>Control</kbd>+<kbd>V</kbd>

Insert text on all lines use <kbd>Shift</kbd>+<kbd>I</kbd> and to delete on all lines use <kbd>d</kbd>

## Resources
Markdown notes (meta/ non-vim) https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

Video about Vim https://www.youtube.com/watch?v=wlR5gYd6um0

Text objects https://blog.carbonfive.com/2011/10/17/vim-text-objects-the-definitive-guide/


{% changed magento/blob/master to magento/raw/master for image to load %}
