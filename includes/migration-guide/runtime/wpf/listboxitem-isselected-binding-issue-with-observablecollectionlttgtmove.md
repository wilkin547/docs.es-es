### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Problema de enlace de IsSelected de ListBoxItem con ObservableCollection&lt;T&gt;.Move

|   |   |
|---|---|
|Detalles|Las llamadas a <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> o <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> en una colección enlazada a un control <xref:System.Windows.Controls.ListBox?displayProperty=name> con elementos seleccionados puede provocar un comportamiento incorrecto en la selección o anulación de selecciones futuras de elementos <xref:System.Windows.Controls.ListBox?displayProperty=name>.|
|Sugerencia|Las llamadas a <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=name> y <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=name> en lugar de a <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> serán la solución alternativa a este problema. Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|

