### <a name="unexpected-invalidcastexception-from-invokemethod-activity-in-wf4"></a>Excepción InvalidCastException inesperada de la actividad InvokeMethod en WF4

|   |   |
|---|---|
|Detalles|El uso de método <xref:System.Activities.Statements.InvokeMethod> que tiene como destino un método con un parámetro que admite un valor NULL puede producir una excepción <xref:System.InvalidCastException?displayProperty=name>.|
|Sugerencia|Este comportamiento se ha revertido en una versión de servicio para .NET Framework 4.5. Para corregir este problema, actualice .NET Framework 4.5 (o actualice a la versión 4.5.1 o posterior de .NET Framework).|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Activities.Statements.InvokeMethod.Parameters?displayProperty=nameWithType></li></ul>|
|Analizadores|<ul><li>CD0088</li></ul>|

