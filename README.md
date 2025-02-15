Redmine LaTeX MathJax Macro Plugin
==================================

This is a simple little plugin which allows mathematical notation to be used within Redmine.

Requirements
------------

Redmine 3.0.x, 3.1.x, 4.0.x, 4.1.x, 5.0.x, 5.1.x or 6.0.x
Other versions are not tested but may work.

Installation
------------
1. Download archive and extract to /your/path/to/redmine/plugins/
2. If you downloaded the zipball (https://github.com/process91/redmine_latex_mathjax/archive/master.zip), rename the extracted directory to 'redmine_latex_mathjax'
3. (Optional) Modify init.rb. For example, if you host MathJax yourself you can point to your own MathJax location.
4. run
     cd /var/www/redmine
     bundle install --without development test --no-deployment
5. run (currently not required) bundle exec rake redmine:plugins NAME=[plugin_name] RAILS_ENV=production
6. (Might be required for Redmine 6.x):
     mkdir /var/www/redmine/plugin_assets/redmine_latex_mathjax
     cp -a /your/path/to/redmine/plugins/redmine_latex_mathjax/assets/* /var/www/redmine/plugin_assets/redmine_latex_mathjax/
7. Restart Redmine (e.g. by restarting Apache)

Login to Redmine and go to Administration->Plugins. You should now see 'Redmine LaTeX MathJax Macro'. Enjoy!

Usage
------------
Anywhere on a wiki or issue page write for formulas:

$mj(\sum_i x_i)$

or a multiline MathJax Syntax:

{{mj(
P_{POWER} =
\cfrac
{U_{POWER}}
{I_{POWER}}
)}}

Hit 'Preview' or 'Save' to see them appear.

FAQ
------------
A: MathJax does not appear in PDFs that are generated by using the PDF link below the wiki pages. 
   See Closed Issue: Formula will not display in PDF export (https://github.com/process91/redmine_latex_mathjax/issues/1#issuecomment-4850823)
   
   Because of the macro this can be fixed in the future by switching from client-side to server-side rendering.

Q: Why a macro? MathJax doesn't need that!

A: The macro is needed to bypass the markup language parser of Redmine.
   For example, Markdown tries to convert underscores to em HTML tags.
   This also opens the possibility for doing server-side rendering in the future.
