# i3 Monitor Manager
This set of shell scripts, and it's associated i3wm config segment are my personal method of
managing how my i3wm workspaces are arranged across multiple monitors. Each workspace is named
according to a naming scheme that is easy to parse in a shell script. The naming scheme is as
follows:
* Each monitor is given a number in the range ```(1-9)```.
* Each workspace for any given monitor is also given a number, also in the range ```(1-9)```.
* Each workspace, across all monitors is given the name ```"$workspace:$monitor-$workspace"```,
* The first ```$workspace``` in the name exists to maintain i3wm workspace sorting order.

## Dependencies
Currently, this set of scripts requires ```jquery``` due to the way that i3wm return information
about workspaces. If you don't want to use ```jquery``` then it should be fairly easy to rewrite
your own version of ```i3mm.getWspaceName``` to avoid using it. I haven't because I already had it
installed, and I just wanted it to work.

## Installation and Usage
Simple enough:
* Throw all of the ```i3mm.*``` shell scripts somewhere on your path - I recommend and personally
  use ```~/.local/bin```
* Add the contents of ```config``` to your i3wm config file. The ```bar{}``` section is not
  required, and exists purely as an example of how to strip the leading ```$workspace``` from the
  displayed workspace name.
* You may need to adjust the keybindings to avoid conflicts, depending on your current setup.

## Where To From Here
Currently, due to the nature of i3wm's config system the sample config only accounts for 3
monitors. In the future, I hope to also create a shell script that will generate the config
section that can then be inserted into the i3wm config at launch. Additionally, the system
currently does not account for changes to monitors. Ideally, this would not be the case.