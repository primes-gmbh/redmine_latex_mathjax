Redmine LaTeX MathJax Plugin
============================
This is a simple little plugin which allows mathematical notation to be used within Redmine.

Installation
------------
1. Download archive and extract to /your/path/to/redmine/plugins/
2. If you downloaded the zipball (https://github.com/vDorst/redmine_latex_mathjax/zipball/master), rename the extracted directory to 'redmine_latex_mathjax'
3. (Optional) Modify init.rb. For example if you host MathJax yourself. You can point to your own MathJax location.
4. Restart Redmine (e.g. by restarting Apache)

Login to Redmine and go to Administration->Plugins. You should now see 'Redmine LaTeX MathJax Macro'. Enjoy!

Usage
------------
Anywhere on a wiki page write for inline formulas:

{{mj(\sum_i x_i$)}}

Hit 'Preview' or 'Save' to make the notation show up.


FAQ
------------
A: They do not show up in PDFs that are generated by using the PDF link below the wiki pages. 
   See Closed Issue: Formula will not display in PDF export (https://github.com/process91/redmine_latex_mathjax/issues/1#issuecomment-4850823)
   
   Because of the macro this can be changed in the future.
   To switch from client-side to server-side rendering.

Q: Why a macro? MathJax don't need that!

A: Macro is needed to bypass the markup language parser of Redmine.
   Like Markdown tries to convert underscores to em HTML tags.
   Also this enables us to do server-side rendering in the future.
