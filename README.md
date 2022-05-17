# Grid for Blazor - How to save/load a grid's layout information


This example illustrates how to use the [LayoutAutoSaving][0] and [LayoutAutoLoading][1] events and the [SaveLayout][3] and [LoadLayout][4] methods to save layout information to some storage. After that this information can be restored and applied to DxGrid. 

This example also illustrates the capability of the GridPersistentLayout class to modify the saved layout.


## Files to Look At

- [Grid.razor](./SaveAndRestoreLayout/SaveAndRestoreLayout/Pages/Grid.razor)
- [UserLayoutManager.cs](./SaveAndRestoreLayout/SaveAndRestoreLayout/Data/UserLayoutManager.cs)


*Note: as this example illustrates a general approach, layout information is stored in the [UserLayoutManager.cs](./SaveAndRestoreLayout/SaveAndRestoreLayout/Data/UserLayoutManager.cs) singleton service. This service doesn't identify the current end user.*

The [Grid.razor](./SaveAndRestoreLayout/SaveAndRestoreLayout/Pages/Grid.razor) page contains two DxGrids.

* The first grid handles the [LayoutAutoSaving][0] and [LayoutAutoLoading][1] events. The current layout information is stored in the singleton service and is restored from this service inside these event handlers. So end-user modifications (paging/sorting/grouping/filtering) will be restored automatically after a page reload. _In the LayoutAutoLoading event, the group index is excluded from the list of saved column layout settings._

* The second grid saves and loads layout information using external buttons where the [SaveLayout][2] and [LoadLayout][3] methods are called. Click the "Save current layout" button to save the current layout information. _When the grid's layout is saved, the column's sort index is excluded from the list of saved column layout settings._ The corresponding item will be created in the external list box. Then select any item in this list box and click the "Load layout" button to load the corresponding layout information. 

[0]: 
[1]: 
[2]: 
[3]: 
