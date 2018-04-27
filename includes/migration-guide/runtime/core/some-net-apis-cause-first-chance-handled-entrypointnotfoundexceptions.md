### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Algunas API de .NET generan primeras excepciones EntryPointNotFoundExceptions (controladas)

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, un pequeño número de métodos de .NET comenzaron a iniciar primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=name>. Estas primeras excepciones se controlaban dentro de .NET Framework, pero podían interrumpir la automatización de pruebas que no las esperasen. Estas mismas API interrumpen algunos escenarios de ApiVerifier con el elemento HighVersionLie habilitado.|
|Sugerencia|Este error puede evitarse actualizando a .NET Framework 4.5.1. Como alternativa, se puede actualizar la automatización de pruebas para que no se interrumpa con las primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li></ul>|

