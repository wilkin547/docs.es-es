### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Incapacidad intermitente para desplazarse hasta el último elemento de instancias ItemsControl (como ListBox y DataGrid) al usar elementos DataTemplate personalizados

|   |   |
|---|---|
|Detalles|En algunos casos, un error de .NET Framework 4.5 impide que las instancias de ItemsControl (como <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name>, <xref:System.Windows.Controls.DataGrid?displayProperty=name>, etc.) se desplacen hasta su último elemento cuando se usan elementos DataTemplate personalizados. Si se trata de efectuar el desplazamiento una segunda vez (después de haber vuelto arriba), sí funciona.|
|Sugerencia|Este problema se resolvió en .NET Framework 4.5.2, por lo que otra posible solución es actualizar a esta versión (u otra posterior) de .NET Framework. Los usuarios también pueden arrastrar las barras de desplazamiento hasta los últimos elementos de estas colecciones, pero puede ser posible que tengan que hacerlo dos veces para conseguirlo.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

