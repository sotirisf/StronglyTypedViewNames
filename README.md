# StronglyTypedViewNames

A T4 template to generate constants for view paths in asp.net MVC (plus some controller names)

This is a simple, but useful T4 template you can use to generate constants representing view name paths so you don't have to use magic strings in your code.
It also generates controller names in the same project the views are in (if any) as a bonus :)

Before running it, there are three variables you should define at the start of the code:

**ProjectName**: The name of the project your T4 file will be in. E.g. "DotSee.StronglyTypedViewNames". I usually prefer to have strongly typed views either in their own project or a commonly used project that can be referenced by all other projects in the solution. 
    
**RelativeViewsFolder**: The folder the views are in. Start from the solution level, e.g. "MyWebProject/Views".

**ControllersFolderName**: The folder controllers are in. E.g. "Controllers". This will generate controller names as well (but not action names). All projects in the solution will be included as long as the same folder name is used for controllers in each project.

This T4 template was based on the well-known T4MVC project, in an attempt to simplify the generation process and overcome some limitations that project's template had. It's really simple, but does its job well.

 
 Here's a sample of what the generated code looks like:
 
  ```  
  public const string Views_Shared_Molecules__SectionTitle = "~/Views/Shared/Molecules/_SectionTitle.cshtml"; 
   
  public const string Views_Shared_Organisms__Contact = "~/Views/Shared/Organisms/_Contact.cshtml"; 
   
  public const string Views_Shared_Organisms__ListFilters = "~/Views/Shared/Organisms/_ListFilters.cshtml"; 
   
  public const string Views_Shared_Organisms__ListFiltersForSearch = "~/Views/Shared/Organisms/_ListFiltersForSearch.cshtml"; 
   
  public const string Views_Shared_Organisms__SearchResultsList = "~/Views/Shared/Organisms/_SearchResultsList.cshtml"; 
   
  public const string Controllers_DotSee_PageMetas__Hreflang = "Hreflang"; 
   
  public const string Controllers_DotSee_PageMetas__PageMetas = "PageMetas";
```

Then, you can go on and use the constants instead of magic strings in your code, making use of AutoComplete in Visual Studio as well:

In views (example from Umbraco CMS view):
```
 @Html.Partial(ViewNameConstants.Views_Shared_Molecules__SectionBlockTitleAlt, Model)
```

In controllers (example from Umbraco CMS Surface controller):
```
return PartialView(MVC.Partials.Views.Widgets.NcWidgetCategoriesList, viewModel);
```
 
