### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>Las llamadas a DataGrid.CommitEdit desde un controlador CellEditEnding eliminan el foco

|   |   |
|---|---|
|Detalles|Las llamadas a <xref:System.Windows.Controls.DataGrid.CommitEdit> desde uno de los controladores de eventos <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> de <xref:System.Windows.Controls.DataGrid?displayProperty=name> provoca que <xref:System.Windows.Controls.DataGrid?displayProperty=name> pierda el foco.|
|Sugerencia|Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework. Como alternativa, se puede evitar si se selecciona <xref:System.Windows.Controls.DataGrid?displayProperty=name> de forma explícita después de llamar a <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|

