`IProjectTreePropertiesProvider` - Visual Studio Next
======================
**Visual Studio 2015:** use [IProjectTreeModifier, IProjectTreeModifier2](IProjectTreePropertiesProvider.md)

**[Item template:](project_item_templates.md)** Project Tree Properties Provider extension

**Scope:** UnconfiguredProject

The `IProjectTreePropertiesProvider` interface can be exported into the 
`UnconfiguredProject` scope to apply cosmetic changes to a project tree 
or one of its nodes. `IProjectTreePropertiesProvider.CalculatePropertyValues` is called back
for every visible and non-visible node in the tree.

This allows you to, for example, set the icon on 
your project's root node to be consistent with your branding by overriding the values set by lower priority providers.
You can also set the icons on specific source items that are may be unique to your project type.

```CSharp
    /// <summary>
    /// Updates nodes in the project tree by overriding property values calcuated so far by lower priority providers.
    /// </summary>
    [Export(typeof(IProjectTreePropertiesProvider))]
    [AppliesTo(MyUnconfiguredProject.UniqueCapability)]
    // TODO: Consider removing the Order attribute as it typically should not be needed when creating a new project type. It may be needed when customizing an existing project type to override the default behavior (e.g. the default C# implementation).
    [Order(1000)]
    internal class ProjectTreePropertiesProvider1 : IProjectTreePropertiesProvider
    {
        /// <summary>
        /// Calculates new property values for each node in the project tree.
        /// </summary>
        /// <param name="propertyContext">Context information that can be used for the calculation.</param>
        /// <param name="propertyValues">Values calculated so far for the current node by lower priority tree properties providers.</param>
        public void CalculatePropertyValues(
            IProjectTreeCustomizablePropertyContext propertyContext,
            IProjectTreeCustomizablePropertyValues propertyValues)
        {
            // Only set the icon for the root project node.  We could choose to set different icons for nodes based
            // on various criteria, not just Capabilities, if we wished.
            if (propertyValues.Flags.Contains(ProjectTreeFlags.Common.ProjectRoot))
            {
                // TODO: Provide a moniker that represents the desired icon (you can use the "Custom Icons" item template to add a .imagemanifest to the project)
                propertyValues.Icon = KnownMonikers.JSProjectNode.ToProjectSystemType();
            }
        }
    }
```

Do NOT use this to modify the structure of the tree. Adding, removing, or
moving nodes in the tree in a modifier will most likely cause malfunctions
in the project system. 

You can create an `IProjectTreePropertiesProvider` export using the "Project Tree
Modifier extension" item template included in the CPS SDK.
