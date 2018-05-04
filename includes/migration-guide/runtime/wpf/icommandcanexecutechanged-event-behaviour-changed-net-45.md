### <a name="icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>Cambio de comportamiento del evento ICommand.CanExecuteChanged en .NET Framework 4.5

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, los elementos <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> se omitían a menos que el remitente del evento fuese el mismo objeto que lo había generado. Este error se ha corregido en actualizaciones de servicio de .NET Framework 4.5.|
|Sugerencia|Este error se corrigió en actualizaciones de servicio de .NET Framework 4.5, por lo que puede evitarse asegurándose de mantener actualizado .NET Framework o actualizando a .NET Framework 4.5.1. También puede modificarse el código de aplicación mediante <xref:System.Windows.Input.ICommand?displayProperty=name> para asegurarse de que el remitente sea el mismo que el objeto que genera el evento al generar un comando <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name>.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=nameWithType></li></ul>|
|Analizadores|<ul><li>CD0084</li></ul>|

