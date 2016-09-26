Oracle PL/SQL
-------------
Based on [oracle-textmate-bundle]

[oracle-textmate-bundle]: https://code.google.com/p/oracle-textmate-bundle/

This extension provides syntax highlighting for PL/SQL files.

Installation
------------
Open the command palette and type:

    ext install plsql

Compiling PL/SQL Files
----------------------
In order to compile a PL/SQL file you need to have an Oracle Client installed and the connection defined in *tnsnames*.

Open a folder in VS Code and in the command pallete type:

    task run

Select **Configure Task Runner**, which will open up the *tasks* file for your project.
Replace the contents of the file with the following code. Make sure you replace the *username* and *password* with your own and the *sid* with the one from your *tnsnames* file.

    {
	    "version": "0.1.0",

	    // The command is a shell script
	    "isShellCommand": true,

	    // Run sqlplus
	    "command": "sqlplus",

	    "args": ["username/password@sid", "@\"${file}\""]
    }

When you want to compile your PL/SQL you can use the command pallete to *Run Task* or *Terminate Task*. You can also define keyboard shortcuts for the two commands in **File > Preferences > Keyboard Shortcuts**.
