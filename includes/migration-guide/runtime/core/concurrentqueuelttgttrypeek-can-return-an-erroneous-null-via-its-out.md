### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek puede devolver un valor NULL erróneo mediante su parámetro out

|   |   |
|---|---|
|Detalles|En algunos escenarios con múltiples subprocesos, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> puede devolver true, pero rellenar el parámetro out con un valor nulo (en lugar del valor correcto observado).|
|Sugerencia|Este problema se corrigió en .NET Framework 4.5.1. Actualizar a esta versión de .NET Framework solucionará el problema.|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

