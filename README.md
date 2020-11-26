# Repeat_Commands
This is a simple plugin that lets you Execute a command or commands multiple times.

# Syntax
#[&lt;start&gt;,]stop[,&lt;step&gt;][,w&lt;wait&gt;] &lt;command&gt;

&lt;start&gt; is the value at which the loop begins. Default is 1.

&lt;stop&gt; is the value at which the loop ends.

&lt;step&gt; is the increment by which the counter changes each iteration. Default is 1 if &lt;start&gt; is less than &lt;stop&gt;, or -1 if it is greater (to count backwards).

&lt;wait&gt; is the number of seconds to pause between executing each command. Default is 0. Does not need to be a whole number (e.g., 1.5 and .2 are valid values).

Any instance of '#' within the command itself is replaced with the current value of the loop counter. (Note that this means you cannot nest loops [e.g., by typing '#3 #5 say hello']. This is intentional.).

Use two semicolons (;;) to insert a literal semicolon within the command.

# Examples
Below is an example of the easiest and most common sort of way you might use this plugin. Really, most people shouldn't need anything more, but it's there just in case.

#3 get bread bag;;eat bread

This will get bread bag;eat bread thre times.  You could add a delay between the eat and following get commands like this:

#3,w1 get bread bag;;eat bread

That will get bread bag;eat bread, wait one second, then get bread bag;eat bread again, wait another second, and get bread bag;eat bread a third time.

Insert '#' into the command to stand for the value of the loop counter variable. In other words, if you wanted to 'where' the first five goblins in the area, you could type this:

#5 where #.goblin

That will execute where 1.goblin, where 2.goblin... where 5.goblin.

Other info and examples are displayed when you install the plugin. Note: the MUD does not like receiving 100 commands in rapid succession. Limit your loops, or at least add a short wait if you really must send all those 100 commands, to avoid being disconnected.
