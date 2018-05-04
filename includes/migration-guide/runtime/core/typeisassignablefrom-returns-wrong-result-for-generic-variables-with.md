### <a name="typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>Type.IsAssignableFrom devuelve un resultado incorrecto para variables genéricas con restricciones

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, <xref:System.Type.IsAssignableFrom(System.Type)> devolverá por error <code>false</code> en todos los casos para algunos tipos genéricos con restricciones.|
|Sugerencia|Este problema se corrigió en una actualización de servicio. Para corregir este problema, actualice .NET Framework 4.5 o actualice a la versión 4.5.1 o posterior de .NET Framework. También puede evitar usar IsAssignableFrom con tipos genéricos que tengan restricciones sobre parámetros genéricos. Se pueden usar API de reflexión a modo de solución alternativa.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Type.IsAssignableFrom(System.Type)?displayProperty=nameWithType></li></ul>|
|Analizadores|<ul><li>CD0089</li></ul>|

