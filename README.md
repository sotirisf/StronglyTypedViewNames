# StronglyTypedViewNames

A T4 template to generate constants for view paths in asp.net MVC (plus some controller names)

This is a simple, but useful T4 template you can use to generate constants representing view name paths so you don't have to use magic strings in your code.
It also generates controller names in the same project the views are in (if any) as a bonus :)

Before running it, there are three variables you should define at the start of the code:

**ProjectName**: The name of the project your T4 file will be in. E.g. "DotSee.StronglyTypedViewNames". I usually prefer to have strongly typed views either in their own project or a commonly used project that can be referenced by all other projects in the solution. 
    
**RelativeViewsFolder**: The folder the views are in. Start from the solution level, e.g. "MyWebProject/Views".

**ControllersFolderName**: The folder controllers are in. E.g. "Controllers". This will generate controller names as well (but not action names). All projects in the solution will be included as long as the same folder name is used for controllers in each project.

This T4 template was based on the well-known T4MVC project, in an attempt to simplify the generation process and overcome some limitations that project's template had. It's really simple, but does its job well.

 
 
