Changes
==========
**Visual Studio "15"**
Download Location: [Visual Studio Project System Extensibility Preview](https://visualstudiogallery.msdn.microsoft.com/43691584-1f0f-46da-adaf-a07c290c1e6e)

* 15.0.594.65117
  * Targets [Visual Studio 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/)
  * [.Net Core project](https://github.com/dotnet/roslyn-project-system) is built on top of CPS
    * App Designer support
    * Nuget support
    * Editing the project file is now possible without unloading the project
  * [File globbing support](doc/overview/globbing_behavior.md)
  * Dynamic Depend Upon Items
  * Folder Properties
  * Extending Xaml rules
* 15.0.183.53925
  * Targets [Visual Studio "15" Preview](https://www.visualstudio.com/en-us/downloads/visual-studio-next-downloads-vs)
  * [Breaking changes](doc/overview/breaking_changes_visual_studio_next.md)
  * `Project Tree Modifier extension` item template was replaced by `Project Tree Properties Provider extension`
  * Other fixes and improvements:
    * [#81](https://github.com/Microsoft/VSProjectSystem/issues/81) - Can't override default Xaml rules; build fails when changing project type to Class Library
    * [#82](https://github.com/Microsoft/VSProjectSystem/issues/82) - Analyzers should support project.json
    * [Connect 2293675](https://connect.microsoft.com/VisualStudio/feedback/details/2293675/cant-add-reference-to-project-created-from-an-extensibility-project-type-template-based-project) Reference Manager Dialog displays error in generated project type

**Visual Studio 2015**
Download Location: [Visual Studio Project System Extensibility Preview](https://visualstudiogallery.msdn.microsoft.com/31e107b7-b0ce-4236-8ffa-ed35f03397b8)
* 14.1.127.50932
  * Targets Visual Studio 2015 Update 2
  * Other fixes and improvements:
    * [#81](https://github.com/Microsoft/VSProjectSystem/issues/81) - Can't override default Xaml rules; build fails when changing project type to Class Library
    * [#82](https://github.com/Microsoft/VSProjectSystem/issues/82) - Analyzers should support project.json
    * [Connect 2293675](https://connect.microsoft.com/VisualStudio/feedback/details/2293675/cant-add-reference-to-project-created-from-an-extensibility-project-type-template-based-project) Reference Manager Dialog displays error in generated project type
* 14.1.80.38181
  * Targets Visual Studio 2015 Update 1
* 14.0.50721.1
  * Targets Visual Studio 2015 RTM
  * New Item Templates
    * [Property Page Value Editor extension](doc/extensibility/property_value_editors.md)
    * [Custom Icons](doc/scenario/provide_custom_icons_for_the_project_or_item_type.md)
    * [Dynamic Enum Values Provider](doc/extensibility/IDynamicEnumValuesProvider.md)
  * Other fixes and improvements
    * Consumes stable versions of [Microsoft.VisualStudio.Threading](https://www.nuget.org/packages/Microsoft.VisualStudio.Threading/) and [Microsoft.VisualStudio.Validation](https://www.nuget.org/packages/Microsoft.VisualStudio.Validation/) Nuget packages
    * `Project Tree Modifier extension` item template - now specifies the `OrderPrecedence` attribute to avoid inconsistent behavior when used in combination with the default project type template
    * `Project Type` template - debugger now functions by default for new project types
    * `Custom Debugger extension` item template - file name now matches the name of the class for the `IDebugLaunchProvider` implementation
    * All item/project templates included in the SDK now use custom icons
* 14.0.50617.1
  * New [Threading Analyzers](https://www.nuget.org/packages/Microsoft.VisualStudio.Threading.Analyzers/)
  * New [Project System Analyzers](https://www.nuget.org/packages/Microsoft.VisualStudio.ProjectSystem.Analyzers)
  * New Item Template: [Command Group Handler extension](doc/extensibility/command_handlers.md)
* 14.0.50430.1
  * Initial release
  
