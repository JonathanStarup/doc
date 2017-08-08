# Syntax Highlighting

Flix currently has limited IDE support, but it is possible to get syntax highlighting.

#### IntelliJ IDEA

Locate your IntelliJ config directory. Depending on the version, it could be
something like `~/.IdeaIC14/config`. Then create the file
`$INTELLIJCONFIG/filetypes/Flix.xml` with the content:

```
<filetype binary="false" description="The Flix Language" name="Flix">
  <highlighting>
    <options>
      <option name="LINE_COMMENT" value="//" />
      <option name="COMMENT_START" value="/*" />
      <option name="COMMENT_END" value="*/" />
      <option name="HEX_PREFIX" value="" />
      <option name="NUM_POSTFIXES" value="" />
      <option name="HAS_BRACES" value="true" />
      <option name="HAS_BRACKETS" value="true" />
      <option name="HAS_PARENS" value="true" />
    </options>
    <keywords keywords="assert;case;def;else;enum;if;in;index;lat;
    let;match;namespace;print;rel;type;val;with" ignore_case="false" />
  </highlighting>
  <extensionMap>
    <mapping ext="flix" />
  </extensionMap>
```

Restart IntelliJ IDEA.

If syntax highlighting doesn't work, then follow these steps:

- Go to `File > Settings > Editor > File Types`.
- Press the "green plus" icon on the right to add a new filetype.
- Enter the following:
    * Name: `Flix`. Description: `The Flix Language`.
    * Line comment: `//`.
    * Block comment start: `/*`. Block comment end: `*/`.
    * Check support `paired braces`, `paired parens`, and `paired brackets`.
    * Add the following keywords:
        * `assert`, `case`, `def`, `else`, `enum`, `if`, `in`, `index`, `lat`, `let`, `match`,  `namespace`, `print`, `rel`, `val`, `with`.
- Press `OK`.

#### Vim

Create the file `~/.vim/ftdetect/flix.vim` with the content:

```
au BufRead,BufNewFile *.flix set filetype=flix
```

Create the file `~/.vim/syntax/flix.vim` with the content:

```
if exists("b:current_syntax")
  finish
endif

syn keyword keywords assert case def else enum if in index lat
syn keyword keywords let match namespace print rel val with

syn region LineComment  start="//" end="$"
syn region BlockComment start="/\*" end="\*/"

let b:current_syntax = "flix"

hi def link keywords Statement

hi def link LineComment  Comment
hi def link BlockComment Comment
```

Ensure that your `~/.vimrc` file contains at least the following:

```
source ~/.vim/syntax/flix.vim
source ~/.vim/ftdetect/flix.vim
syntax on
```

#### Emacs
Create the file `~/.emacs.d/elisp/flix-mode.el` with the following content:

```
(setq flix-keywords '("assert" "case" "def" "else" "enum" "if" "in" "index" "lat"
                      "let" "match" "namespace" "print" "rel" "val" "with"))

;; generate regex string for each category of keywords
(setq flix-keywords-regexp (regexp-opt flix-keywords 'words))

;; create the list for font-lock.
;; each category of keyword is given a particular face
(setq flix-font-lock-keywords
      `((,flix-keywords-regexp . font-lock-keyword-face)))

;;;###autoload
(define-derived-mode flix-mode scala-mode "flix mode"
  "Major mode for editing Flix"
  (setq font-lock-defaults '((flix-font-lock-keywords))))

;; clear memory. no longer needed
(setq flix-keywords nil)
;; clear memory. no longer needed
(setq flix-keywords-regexp nil)

(provide 'flix-mode)
```

Ensure that your `~/.emacs.d/init.el` file contains at least the following:

```
(load-file "$HOME/.emacs.d/elisp/flix-mode.el")
(add-to-list 'auto-mode-alist '("\\.flix\\'" . flix-mode))
```
