### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>La ausencia de moniker de la plataforma de destino da lugar a un comportamiento de la versión 4.0

|   |   |
|---|---|
|Detalles|Las aplicaciones sin un elemento <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> aplicado en el nivel de ensamblado se ejecutarán automáticamente con la semántica (las peculiaridades) de .NET Framework 4.0. Para garantizar una buena calidad, se recomienda que todos los archivos binarios incluyan un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> explícito en el que se indique la versión de .NET Framework con la que se compilaron. Tenga en cuenta que usar un moniker de la plataforma de destino en un archivo de proyecto hará que MSBuild aplique automáticamente un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>.|
|Sugerencia|Se debe proporcionar un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>, agregándolo directamente al ensamblado o especificando una plataforma de destino en el [archivo de proyecto, o bien a través de la GUI de propiedades del proyecto de Visual Studio](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio- managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

