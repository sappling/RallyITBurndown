# RallyITBurndown
Example of a Rally iteration burndown chart integrated into a portal like Confluence

## Usage
These files need to be hosted as static content somewhere, then referenced using an IFRAME from the portal. 
Replace the \_\_INSERT_YOUR_KEY_HERE\_\_ content in index.html with an appropriate login key.  See the [rally documentation](https://help.rallydev.com/loginkey)
for instructions to obtain this key.

In Confluence, reference the static page using an IFRAME macro.  You should provide two parameters:
*  workspace - this should have the value of the workspace object ID
*  project - this should have the value of the project object ID

For example, your iframe URL might end up like: http://myconfluencesite.com/staticcontent/itburndown?project=12312312345&workspace=32132132121

See [this link](http://stackoverflow.com/questions/18830709/find-workspace-an-project-oid) for a description of how to find these IDs.

Note that the javascript used in this project creates an IFRAME, but nesting this inside of another IFRAME still seems to be necessary.  I
found that the javascript Rally uses to create the graph also makes changes to the CSS of the page that contains this inner IFRAME.
If you don't have the extra IFRAME it will mess up your confluence site's look and make it inoperable for some browsers.

This javascript will also use the client's current date to query the project looking for the current iteration.  It displays
the iteration burndown graph for the iteration it finds.

##Credits
Thanks to Steven Levithan for his parseUri utility

The base functionality for embedding a StandardReport came from the [Rally Login-Component-Example](/RallyTools/Login-Component-Example).
