evernote-mode
=============

Emacs interface for Evernote which originally started on
[Google Code][1].  Then it was [updated][2] for working with Ruby
1.9.3 and Emacs 24.1.  Which was then updated to [work with OAuth][3].
Then just a little bit of Emacs customization niceness was added.

INSTALLATION
------------

You will need to install the Evernote OAUTH Ruby gems in order to get
all of this stuff working.  Run the following command:

    gem install evernote_oauth



CONFIGURATION
-------------

You'll need to get a production developer token from [Evernote][4] and
in Emacs set the custom variable `evernote-developer-token`.  If
`evernote-mode` is loaded this can be done easily with `M-x
customize-group evernote`.


.emacs SETUP
-------------
Below is a sample .emacs config file,

<code>
(add-to-list 'load-path "~/.emacs.d/evernote-mode")
(require 'evernote-mode)
(setq evernote-username "<EVERNOTE USERNAME>") ; optional: you can use this username as default.
(setq evernote-enml-formatter-command '("w3m" "-dump" "-I" "UTF8" "-O" "UTF8")) ; option
(global-set-key "\C-cec" 'evernote-create-note)
(global-set-key "\C-ceo" 'evernote-open-note)
(global-set-key "\C-ces" 'evernote-search-notes)
(global-set-key "\C-ceS" 'evernote-do-saved-search)
(global-set-key "\C-cew" 'evernote-write-note)
(global-set-key "\C-cep" 'evernote-post-region)
(global-set-key "\C-ceb" 'evernote-browser)
(custom-set-variables '(evernote-developer-token "<EVERNOTE DEV TOKEN>"))
</code>

In this case, you will also need to install w3m,

     apt-get install w3m

or

     yum install w3m

[1]: http://code.google.com/p/emacs-evernote-mode/ "Original source"

[2]: https://github.com/rubbish/evernote-mode "rubbish/evernote-mode"

[3]: https://github.com/pymander/evernote-mode "pymander/evernote-mode"

[4]: http://dev.evernote.com/doc/articles/authentication.php#devtoken "Evernote Authentication"





