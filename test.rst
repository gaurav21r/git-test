*********
Git Hooks
*********

Git hooks are used within Aspire to validate code before Git operations such as ``push`` ``add`` ``commit``.

The git commit hook does basic checking and linting of the code and commit message. It is engineered to run offline so that offline commits are possible.

The git push hook requires you to be online and actively contacts the GitHub server / issue tracker etc.

git commit Hook
================

This hook will be run when you try to execute a ``git commit -m "your message"``.

Features
--------

* Check if you are trying to directly commit to a restricted branch (like master or dev). |TODO|
  You are supposed to be working on a seperate branch and send a pull request. See `Engineering Ops <http://>`_ for more info.

* Lint your files. Visit `Code Convention <http://>`_ for more info.

	* Each JS file will be linted with JSHint. |TODO| 
	* Each LESS / CSS file will be linted. |TODO|
	* Each HTML file will be linted with tidy. |TODO|
	* You will be informed of the error (file and line number) and it will not allow you to commit. |TODO|

* Check for the commit message to be in a valid format.
  
	* Your commit message must have a valid GitHub issue number (like **#2321**) associated with it.
	* Your commit message must have a valid Documentation Number associated with it (like **doc#2123**). |TODO|
	* Your commit message must be of the proper format like Add / Update / Remove etc. |TODO|
	* Run unit tests on the files that are supposed to be commited and check code coverage and test results. |TODO|
	  

git push Hook |TODO|
====================

This hook will be run when you have added files and commits and are executing a ``git push origin <branchname>``.

Features
--------

* The hook requires that you have a valid internet connection, which is quite obvious since you are trying to push to the server.

* It will verify your identity with a prompt for username. This will take care of any wrong commit owners due to ``git config``.

* It will check the GitHub issue numbers and Documentation numbers in each of the Commit Messages and 
	
	* Check whether the Github Issue numbers belong to you or you have access to solve them.
	* Check that the Documentation Numbers tally with the issue numbers. 
	  
Incase of Error
---------------


.. |TODO| replace:: *(Yet to be implemented)*
