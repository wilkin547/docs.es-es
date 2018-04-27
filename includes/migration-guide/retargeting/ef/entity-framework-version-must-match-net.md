### <a name="entity-framework-version-must-match-the-net-framework-version"></a>La versión de Entity Framework debe coincidir con la versión de .NET Framework

|   |   |
|---|---|
|Detalles|La versión de Entity Framework se debe hacer coincidir con la versión de .NET Framework. Para .NET 4.5 se recomienda Entity Framework 5. Hay algunos problemas conocidos con EF 4.x en un proyecto de .NET 4.5 relacionados con <xref:System.ComponentModel.DataAnnotations>. En .NET 4.5, estos se movieron a otro ensamblado, por lo que hay problemas a la hora de determinar qué anotaciones se van a usar.|
|Sugerencia|Actualizar a Entity Framework 5 para .NET Framework 4.5|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Redestinación|

