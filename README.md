indent/html.vim : alternative html indent script
================================================

Mirror of Andy Wokula's [indent/html.vim](http://www.vim.org/scripts/script.php?script_id=2075 
"Andy Wakula's index/html.vim script on vim.org"). Mirrored on

Created By
----------

[Andy Wokula](http://www.vim.org/account/profile.php?user_id=8357)
 
Script Type
-----------

indent
  
Description
-----------

This script is based on the distributed indent scripts for HTML (and CSS). The 
original script becomes very slow when indenting more than a few lines, thus 
here is an improvement. 

Customization:
--------------

Variables you can set in the vimrc.  Given values are examples to change 
the defaults. 

Note: This applies to v0.6 (!).  Earlier version used `:IndHtmlLocal` for 
customization.  Details can always be found in the script header. 

You can set the indent for the first line after `<script>` and `<style>`
"block tags" (default "zero"): 

    :let g:html_indent_script1 = "inc" 
    :let g:html_indent_style1 = "inc" 

VALUE MEANING 
-------------

* `zero` zero indent 
* `auto` auto indent (same indent as the blocktag) 
* `inc` auto indent + one indent step 

The following `<tags>` increase the indent (for what follows) per default (taken
from the original script, but slightly modified): 

    a, abbr, acronym, address, b, bdo, big, blockquote, button, caption, 
    center, cite, code, colgroup, del, dfn, dir, div, dl, em, fieldset, font, 
    form, frameset, h1, h2, h3, h4, h5, h6, i, iframe, ins, kbd, label, legend,
    map, menu, noframes, noscript, object, ol, optgroup, q, s, samp, select, 
    small, span, strong, sub, sup, table, textarea, title, tt, u, ul, var, th, 
    td, tr, tfoot, thead 

(added with v0.8): 

    area, article, aside, audio, bdi, canvas, command, datalist, details, embed, 
    figure, footer, header, group, keygen, mark, math, meter, nav, output, 
    progress, ruby, section, svg, texture, time, video, wbr, text 

You can add further tags with 

    :let g:html_indent_inctags = "html,body,head,tbody" 

the original script uses the `g:html_indent_strict` variable to include these tags 

You can remove tags with 

    :let g:html_indent_autotags = "th,td,tr,tfoot,thead" 

the original script uses the `g:html_indent_strict_table` variable to include these tags 

Default value is empty for both variables.  The default tags that increase indent are defined once per session only. 


Problems and Bugs: 
------------------

* still no indent rules for attributes spanning several lines 
* sometimes `cindent()` thinks it is better to use zero indent for what follows ... 
* some tags increase indent per default, but their closing tag is optional, 
  e.g. `<td>` -- the script cannot detect missing closing tags 


Suggestions, bug reports welcome (I'm not writing HTML regularly).

Install Details
---------------

### Old School Installs

#### Unix

Copy script to ~/.vim/indent 

#### Win:

Copy script to ~\vimfiles\indent 

### Install via Pathogen

1. Follow the instructions to install [Pathogen](https://github.com/tpope/vim-pathogen#installation "Pathogen Installation")
1. 
    Clone the `vim-indent-html` repository
      
        $ mkdir -p ~/.vim/bundle
        $ cd ~/.vim/bundle
        $ git clone git://github.com/bitfyre/vim-indent-html.git
  
### Install via Vundle

1. Add `Bundle 'bitfyre/vim-indent-html'` to your `~/.vimrc`
1. Do one of the following
    * Within vim run `:BundleInstall`
    * From your shell run `vim +BundleInstall +qall

Enable Filetype Detection
-------------------------

Enable filetype detection and use of indent plugins: 

    :filetype indent on

