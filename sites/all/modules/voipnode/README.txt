
== Introduction ==

The VoIP Node module uses the VoIP Extension API (defined by voipextension.module) to provide phone extensions to CCK content types.

In addition to extension numbers and the other elements provided by the API, this module adds 3 new audio fields to each node extension:
* a field that might store an audio recording with the name of the node (field_voipnode_aname); something that could be played nicely over the phone
* a field that might store an audio description of the node (field_voipnode_adesc); something that migth be played as part of audio directories, and
* a field that might store an audio greeting message (field_voipnode_agreet), something like "welcome to John’s extension," or "sales department,"that might be played whenever a caller is directed to the extension.

The VoIP Extension module comes with a simple directory that lists all the VoIP Nodes in the system with their respective extension fields.  It also provides support for the creation of custom pages through the Drupal Views system.


== Installation ==

VoIP Node module should be downloaded and enabled just like any other Drupal module.


== Configuration ==

A. Adding extensions to CCK content types

In order to add a VoIP  extension to an existing "mytype" content type:

1. Go to admin/content/node-type/mytype
2. Click on the "VoIP Node" link down in the page
3. Check the "Use this content type as a VoIP Node" box
4. Set "VoIP Node Default Settings" as needed
4.1 Select the default script name that will be used for that content type
4.2 Define whether extensions of the present kind should be listed in the extension’s directory by default
5. Save the changes
6. If needed, "reindex" the extensions of that content type (see section D below)

B. Changing the extension settings associated with individual VoIP Nodes

In order to make an individual VoIP Node behave differently from the default defined for its content type:

1. Open the node for editing by going to /node/<mynodeid>/edit
2. Open the "VoIP Extension Settings" section of the form
3. Change the values as desired
4. Save the changes


C.  System-wide configuration

To set the default values that will be used by any new VoIP content type created in the system:

1. Go to /admin/settings/voipnode/defaults
2. Set the options as desired
3. Save the changes


D. The importance of "reindexing" VoIP Node extensions

Some times it is necessary to "reindex" (or reset) extensions of certain content types. That is particularly the case when
a) Extensions are enabled for content types that already have content instances available in the system;
b) The admin needs to reset the scripts associated with extensions of a given content type

When "reindexing extensions," the system adds extensions to any nodes in the content type that do no not have them yet, and resets all nodes to the content-type defaults.

To "reindex" a content type:
1. Go to admin/settings/voipnode/reindex
2. Select the content type to be reindexed
3. Press the "Confirm" button


E. Configuring the VoIP Node audio fields

To change the widgets, formaters or any of the settings associated with the special audio fields defined by VoIP Node extensions:

1. Go to admin/content/node-type/mytype
2. Select "VoIP Node"
3. Select "VoIP Directory Fields Configuration"
4. Select the audio field to be modified
5. Change the audio field settings as needed
6. Save the changes


== Accessing the default VoIP Node directory ==

1. Go to /admin/build/modules/ and enable the Views UI module
2. Go to /admin/build/views/list and enable the voipnode_directory view
3. Access the VoIP Node directory by going to /voip/extension/node


== About ==

This module has been originally designed and implemented by the MIT Center for Civic Media (http://civic.mit.edu/) as part of the VoIP Drupal (http://drupal.org/project/voipdrupal/) initiative.

