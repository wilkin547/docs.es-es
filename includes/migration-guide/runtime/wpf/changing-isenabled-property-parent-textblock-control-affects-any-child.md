### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>El cambio de la propiedad IsEnabled del elemento primario de un control TextBlock afecta a todos los controles secundarios

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6.2, el cambio de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> del elemento primario de un control <xref:System.Windows.Controls.TextBlock?displayProperty=name> afecta a todos los controles secundarios (como los hipervínculos y los botones) del control <xref:System.Windows.Controls.TextBlock?displayProperty=name>. En .NET Framework 4.6.1 y versiones anteriores, los controles dentro de un <xref:System.Windows.Controls.TextBlock?displayProperty=name> no siempre reflejaban el estado de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> del elemento <xref:System.Windows.Controls.TextBlock?displayProperty=name> primario.|
|Sugerencia|Ninguno. Este cambio se ajusta al comportamiento esperado de los controles dentro de un control <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|

