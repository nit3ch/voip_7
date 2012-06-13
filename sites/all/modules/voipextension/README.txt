
== Introduction ==

The VoIP Extension module provides a basic API that enables Drupal modules to assign phone extension numbers to nodes, users, views, and other elements of the system.

Extension management is done via a hook_menu() like interface that might be called by the different modules in the system.

In particular, extensions are arrays that include the following fields:
* eid, the extension number and primary identifier
* module, with the name of the module the extension is associated with (i.e, "node", "user", etc.)
* module_id, an id for this extension as defined by, and for use by, the module (for instance, extensions from module "node" might use module_id to store the nid of the node)
* extension_type, the type of the extension as defined by the module (for instance, "node" extensions might use this field to store the type of the node associated with the extension, ie. "page", "story", etc.)
* title, the default, text-based title of the extension
* title_callback, a callback to change the title dynamically. Can be used to, among other things, return an audio file to be played whenever the title is needed.
* description, brief text describing the extension. Useful in, among other things, the creation of extension directories
* description_callback, callback to change the description, and set audio description.
* directory_type, how and if the extension should be listed in the directory
* enabled, boolean indicating whether the extension is enabled.
* script, the name of the VoIP Drupal script that should be executed whenever a caller goes to this extension
* script_callback, callback that returns the name of the script
* script_arguments, array with the arguments to be used whenever the script is loaded

The VoIP Extension module comes with a simple default phone directory.  It also provides support for the creation of custom pages through the Drupal Views system.


== Accessing the default VoIP extension directory ==

1. Go to /admin/build/views/list
2. Enable the voipextension_directory view
3. Access the directory of all the extensions in the system by going to /voip/extension


== About ==

This module has been originally designed and implemented by the MIT Center for Civic Media (http://civic.mit.edu/) as part of the VoIP Drupal (http://drupal.org/project/voipdrupal/) initiative.
