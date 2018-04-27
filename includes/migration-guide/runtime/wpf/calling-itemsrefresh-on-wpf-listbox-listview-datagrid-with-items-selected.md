### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Llamar a Items.Refresh en un elemento ListBox o ListView, o una cuadrícula de datos de WPF con elementos seleccionados puede hacer que aparezcan elementos duplicados en el elemento

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, llamar a ListBox.Items.Refresh desde el código con elementos seleccionados en un elemento <xref:System.Windows.Controls.ListBox?displayProperty=name> puede hacer que los elementos seleccionados se dupliquen en la lista. Se produce un problema similar con <xref:System.Windows.Controls.ListView?displayProperty=name> y <xref:System.Windows.Controls.DataGrid?displayProperty=name>. Este problema se corrigió en .NET Framework 4.6.|
|Sugerencia|Una solución alternativa para este problema consiste en, mediante programación, anular la selección de los elementos antes de llamar a <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> y volver a seleccionarlos después de que la llamada se complete. Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|

