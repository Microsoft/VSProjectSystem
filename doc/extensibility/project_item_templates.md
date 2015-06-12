Item Templates
====================

The Project System Extensibility SDK offers several item templates.

They can be easily added to your project by using Add New Item. They are located under the Visual C# Items/Extensibility/Project System Node in the Add New Item dialog.

Item Template | Description | More Info
------------ | ------------- | -------------
Project Item Type | Defines new types of items that can be added to your project | [Custom Item Types](custom_item_types.md), [Tutorial](../overview/contentitem_types.md)
Build Up-To-Date Check extension | Provides a hint as to whether the project's outputs are up to date | [IBuildUpToDateCheckProvider](IBuildUpToDateCheckProvider.md)
Project Capabilities Provider extension | Export that can declare capabilities on behalf of a project | [IProjectCapabilitiesProvider](IProjectCapabilitiesProvider.md)
Project Deploy extension | Export that define the deploy step for a project | [IDeployProvider](IDeployProvider.md)
Project Load Veto extension | Export that can prevent loading a project in Visual Studio | IVetoProjectLoad
Project Tree Modifier extension | Export that can tweak the appearance of your project in the Solution Explorer | [IProjectTreeModifier](IProjectTreeModifier.md)
Special Files Provider extension | Export than can identify certain well-known files in a project | ISpecialFileProvider
Xaml Rule | Creates an empty xaml rule | [Property Pages](property_pages.md)
Custom Debugger extension | Export that defines the debug step for a project | [IDebugLaunchProvider](IDebugLaunchProvider.md)

### Future Item Templates
Item Template | Description | More Info
------------ | ------------- | -------------
Command Group Handler extension | Export that defines command handling for a group of commands | [Command Handlers](command_handlers.md)