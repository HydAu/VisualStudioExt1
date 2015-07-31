
# Title: Caret Fish Eye Provider Sample
**Abstract:** Demonstrate how to implement the Line Transformation API. [ View this sample online](https://github.com/Microsoft/VSSDK-Extensibility-Samples).

* Technologies: Visual Studio 2015 SDK
* Topics: Visual Studio Editor, VSX
* Last Updated: 05/15/2015

**Description**

This sample extension for Visual Studio 2015 modifies the text editor using
the Line Transformation API. The extension visually scales lines so that they
gradually appear smaller as they get farther away from the text caret.



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

  1. To run the sample, hit **F5** or choose the **Debug &gt; Start Debugging** menu command. A new experimental instance of Visual Studio will launch. 
  2. Once loaded, open any file in the **Text Editor**
  3. Move the text caret around the screen 
  4. Compare the text size of the line that the caret is currently on to the size of surrounding lines 



**Project Files**

* **AssemblyInfo.cs**

This file contains assembly custom attributes.

* **CaretFisheyeLineTransformSource.cs**

This class derives from ILineTransformSource, and implements all of the
functionality of Caret Fish Eye

* **CaretFisheyeLineTransformSourceProvider.cs**

This class a connector that produces the CaretFisheye
LineTransformSourceProvider



**Functional Tests**

  * Verify the sample builds in all configurations
  * Verify that the sample was registered. The About box should list the product as installed
  * Verify that lines visually change in size as the caret is moved about the screen 



**Related topics**

  * [ Editor Documentation ](https://msdn.microsoft.com/en-us/library/dd885118(v=vs.140).aspx)
  * [ Visual Studio SDK Documentation ](https://msdn.microsoft.com/en-us/library/bb166441(v=vs.140).aspx)



