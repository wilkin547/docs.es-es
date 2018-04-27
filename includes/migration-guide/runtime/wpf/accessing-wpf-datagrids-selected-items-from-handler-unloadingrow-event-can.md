### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>El acceso a los elementos seleccionados de un control DataGrid de WPF desde un controlador del evento UnloadingRow del control DataGrid puede producir una excepción NullReferenceException

|   |   |
|---|---|
|Detalles|Debido a un error de .NET Framework 4.5, los controladores de eventos para los eventos <xref:System.Windows.Controls.DataGrid> en los que se elimina una fila pueden provocar que se inicie una excepción <xref:System.NullReferenceException?displayProperty=name> si tienen acceso a las propiedades <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> de <xref:System.Windows.Controls.DataGrid>.|
|Sugerencia|Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|

