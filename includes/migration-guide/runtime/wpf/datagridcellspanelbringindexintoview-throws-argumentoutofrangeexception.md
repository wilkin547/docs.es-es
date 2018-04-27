### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView inicia una excepción ArgumentOutOfRangeException

|   |   |
|---|---|
|Detalles|<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funcionará de forma asíncrona cuando se habilite la virtualización de columnas pero el ancho de las columnas todavía no se haya determinado.  Si se quitan las columnas antes de que se complete la operación asíncrona, se puede iniciar una excepción <xref:System.ArgumentOutOfRangeException?displayProperty=name>.|
|Sugerencia|Siga uno de estos pasos:<ol><li>Actualice a .NET 4.7.</li><li>Instale la revisión de reparación más reciente para .NET Framework 4.6.2.</li><li>Evite quitar las columnas hasta que se haya completado la respuesta asíncrona para <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|

