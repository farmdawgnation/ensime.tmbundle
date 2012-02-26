ENSIME TextMate Bundle
======================

This is a fork of the bundle originally written by mads397. You can find the original bundle [here](https://github.com/mads379/ensime.tmbundle). Additionally, you can see a preview video of the bundle in action [here](http://www.youtube.com/watch?v=sIp-Xt3TvrI).

I (Matt Farmer) am currently in the process of updating this bundle to support the latest version of the swank protocol. I'm working against ENSIME 0.9.2 RC2 for Scala 2.8. My plans
are to provide further enhancements to this bundle after the original functionality is restored.

Using it
--------

**NOTICE**: You need to have an .ensime project file in the root of your project. For more information about this file please read the [ENSIME manual](http://aemon.com/file_dump/ensime_manual.html#tth_sEc3 "ENSIME manual"). If you're using the SBT build system, you should be able to install
the ensime plugin. Details are in the README of the [ENSIME project](https://github.com/aemoncannon/ensime "ENSIME GitHub Page"). To generate your .ensime
file simply open up sbt in interactive mode and run `ensime generate` from your project root.

**Aside:** I've seen some weirdness in projects I'm working on where sbt wraps everything in a subproject directive inside the .ensime file. I haven't figured
out if this is a bug in my project configuration or if it is a bug in sbt 0.11.2, but if you see this happen just manually edit the .ensime file to fix it.

Now open a file file in that project and hit ⌃⇧R and chose "Start ENSIME". This will start the ENSIME backend and the output will be written in a HTML output window. You can safely minimize this window now. Now initialize ENSIME by hitting ⌃⇧R and pick the command "Initialize ENSIME". This will send your project file to ENSIME and it will start analyzing your code. After a few seconds ENSIME is ready to help you out.

- **Refactoring**
  - Organize imports (⌃⇧H): This will organize your imports and remove any unused imports. *(working)*
  - Reformat Document (⌃⇧H): This will reformat the current document. *(untested)*
  - Rename (⌃⇧H): This will rename the selected text. *(working)*
- **Other**
  - Navigation (⌘⇧C): Works just like Go-to-file expect it knows about the classes/objects/traits/etc. in your project. This will show all of the members in all of the packages in your project. You can navigate the list using the arrow-keys and filter it using the search field at the top. Hitting enter will open the file where the selected item was declared and move the caret to the appropriate line. *(working)*
  - Inspect (⌃⇧i): This will show a tooltip with the type of the expression under the caret. *(working)*
  - Type check project(⌃⇧V): This will type check your project. If there are any errors it will display a drop-down list with the errors. If you pick one of the items it will jump to that line in the file with the error. *(type check occurs, but doesn't display results properly)*
  - Code completion (⌥+⎋): This will do code-completion or either types or methods depending on when you call it. *(not working)*


Installation 
------------

First, you'll need to install ENSIME. You can hop over to the [ENSIME GitHub page](https://github.com/aemoncannon/ensime "ENSIME GitHub Page") and download a copy. I'm working
against 0.9.2 RC2. After you download ENSIME, unzip it wherever you like.

To install the bundle simply run the following in your terminal:

<pre><code>git clone https://github.com/mads379/ensime.tmbundle.git
open ensime.tmbundle</code></pre>

Add the shell variable ENSIME_HOME in TextMate -> Preferences... -> Advanced -> Shell Variables to the root of your ENSIME distribution (This would be the path to the folder you just unpacked). For me this is <code>/Users/matt/ensime_2.8.3-SNAPSHOT-0.9.3.RC2</code>

About
------------

This bundle takes advantage of the [ENSIME backend](https://github.com/aemoncannon/ensime "ENSIME backend") to bring IDE features to TextMate Scala projects.