Modules are contained in the **./lib/modules/* ** folder. The template.py file has detailed information on a module's structure and what it should contain:

[[https://github.com/EmpireProject/Empire/wiki/Images/empire_template.png|align=center]]

Additional options go in self.options after the **Agent** argument. A module like **./lib/modules/situational_awareness/userhunter.py** has an example of this. If the argument is required for execution, set Required to True, and if you want a default value filled, set Value.

In the generate() method, the script variable holds the main PowerShell script you want to run. End this script with the main function you want run, with no spaces after the triple quotes, e.g. Invoke-Something""". If your PowerShell script is large or reused by multiple modules, consider placing it in the **./data/module_source/* ** directory and reading it in as a resource.

If any of your options need special manipulation, modify the for option,values in self.options.iteritems(): code. For example, the credentials/mimikatz/golden_ticket needs some options tacked on in a special format, so it handles them accordingly.

You might have to play around with the formatted output for your module, e.g. **collection/filefinder** needs to append script += " | Out-String" to format the output correctly.

While testing, if you modify the PowerShell script itself, you don’t need to reload anything to retest running on an agent. If you modify the Python wrapper for the module, you can do **reload** in the module menu to reload the module.py file itself.