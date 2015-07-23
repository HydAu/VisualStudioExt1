
# Title: Build Progress Bar Sample
**Abstract:** Display a Progress Bar inside a Toolwindow.[ View this sample online](https://github.com/Microsoft/VSSDK-Extensibility-Samples).

* Technologies: Visual Studio 2015 SDK
* Topics: Visual Studio Shell, VSX
* Last Updated: 05/11/2015


**Description**

This Visual Studio Package provides a new tool window called "Build Progress".
The window displays a WPF ProgressBar that indicates percentage completion of
the current solution build.

**Requirements**

[ Visual Studio 2015 ](http://www.microsoft.com/visualstudio/en-
us/try/default.mspx#download)

[ Visual Studio 2015 SDK ](https://www.visualstudio.com/en-us/downloads
/visual-studio-2015-downloads-vs.aspx)



**Build the sample**

  * Download the zip file associated with the sample 
  * Unzip the sample to your machine 
  * Double click on the .sln file to launch the solution 



**Run the sample**

  1. To run the sample, hit F5 or choose the **Debug &gt; Start Debugging** menu command. A new instance of Visual Studio will launch under the experimental hive. 
  2. Once loaded, choose the **View &gt; Other Windows &gt; Build Progress** menu command.
  3. A new tool window called "Build Progress" will open, displaying a WPF ProgressBar control. You can move, resize, or dock this tool window however you like. 
  4. Open an existing buildable solution or create a new one using the **File &gt; New &gt; Project** menu command. 
  5. Once the solution has loaded, build the solution by running the **Build &gt; Build Solution** menu command. 
  6. You should see the progress bar's value and text change as each project in the solution is built. The file is displayed in the editor with colored text 



**Source Code Overview**

The source code in this sample demonstrates several techniques you can use to
write your own packages:

  * How to add a menu command to the **View &gt; Other Windows** menu group. 
  * How to display WPF content on a tool window 
  * How to monitor solution load/unload events 
  * How to monitor solution build events 
  * How to check and monitor the value of a Visual Studio Shell property (VisualEffectsAllowed)

Our Visual Studio Package implements the interfaces
**IVsShellPropertyEvents**, **IVsSolutionEvents**, and
**IVsUpdateSolutionEvents2** so that it can receive notification of shell
property changes, solution load/unload events, and solution build events. In
order to receive calls to these interface methods, it must advise the
appropriate service providers that we want to be notified, as demonstrated in
ProgressBarPackage's Initialize method.

We monitor the value of the VisualEffectsAllowed shell property in order to
modify how the progress bar is displayed. We also monitor solution load/unload
events to keep track of how many projects are currently loaded in the
solution. Lastly, we monitor solution build events in order to update the
value and text of the progress bar.



**Project Files**

* **BuildProgressBar.vsct**

Defines layout and type of commands in the package, namely the Build Progress
menu command

* **BuildProgressToolWindow.cs**

Implements the tool window functionality, and owns an instance of the
ProgressBarControl

* **ProgressBarControl.xaml**

Defines the XAML for the ProgressBarControl, which is the content hosted on
the tool window

* **ProgressBarControl.xaml.cs**

Defines the code-behind for the ProgressBarControl. This gives us greater
control over the behavior of the ProgressBarControl

* **ProgressBarPackage.cs**

Implements the Visual Studio Package, where we monitor events



**Related topics **

* [ Tool Window Documentation ](https://msdn.microsoft.com/en-
us/library/bb165390(v=vs.140).aspx)

* [ Visual Studio SDK Documentation ](https://msdn.microsoft.com/en-
us/library/bb166441(v=vs.140).aspx)



