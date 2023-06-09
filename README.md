# sphinxcontrib-hoverrole
A Sphinx extension for providing translations when hovering
Warning: This extension requires Python 3!

This module is an extension for Sphinx. It defines a role :hover: which takes a single string argument of the form `arg1,arg2`. 
The directive .. hoverlist:: is also defined and contains a list of terms translated by :hover: along with their translations.

In the Sphinx-generated HTML code the string 'arg1' is highlighted and will provide a translation of 
the string 'arg2' to English (from Icelandic) on mouse-over based on the stae.is/os database (stored locally in 'ordasafn.py'). 
If no comma is found in the argument, 'arg2' is assumed to be the same as 'arg1'.
You can also add a non-negative integer to indicate the index of the entry wanted, f.ex. 
    :hover:`Mengi, mengi, 5` náttúrulegu talnanna er táknað með...
would fetch the 5th entry of the translation of "mengi". 
If no integer index is provided, all available translations are shown.


The extension recognizes the following user settings which can be set in conf.py:

hover_numOfTranslations, default:'single' 
Set to 'all' to include all matches found in the dictionary instead of only the top one.

hover_htmlLinkToStae, default 1 
Set to 0 to disable stae.is link in HTML output.

hover_latexItText, default 1
Set to 0 to disable italicization of terms in Latex output.

hover_latexLinkToStae, default 0
Set to 1 to enable stae.is link in Latex output. 
Overrides hover_latexItText.

hover_translationList, default 1
Set to 0 to remove all translation lists.
.. hoverlist:: can still be called but will not output anything.

hover_miniTranslationList, default 0
Set to 1 to make the list of translations smaller in HTML output. 
(Each term is put in a seperate line instead of in a paragraph).



Example:
========
Ef gefinn er rétthyrndur þríhyrningur segir reglan til um að ef lögð eru saman önnur 
veldi :hover:`skammhliða,skammhlið` þríhyrningsins jafngildi sú summa öðru :hover:`veldi` langhliðarinnar.



Installation:
=============
1. Navigate to the folder containing this README file.
2. Run the following commands:
	>>python setup.py build
	>>sudo python setup.py install
3. Move 'layout.html' to your '_templates' directory. If there already exists a custom layout file then copy the contents of 'layout.html' to that file.
4. Add 'hoverrole.hoverrole' to your extensions in 'conf.py'



Possible additions:
============================
- Support for other dictionaries. Possibly BÍN look-up for search-terms (See: bin.arnastofnun.is/ ).
- English-to-Icelandic translation.
- Python 2 suppport.
