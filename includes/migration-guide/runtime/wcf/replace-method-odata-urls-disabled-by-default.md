### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>El método Replace de las direcciones URL de OData está deshabilitado de forma predeterminada

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, el método Replace de direcciones URL de OData está deshabilitado de forma predeterminada. Cuando el método Replace de OData esté deshabilitado (ahora, de forma predeterminada), cualquier solicitud de usuario, incluidas las funciones Replace (que son poco frecuentes), generará un error.|
|Sugerencia|Si el método Replace es necesario (lo que es poco frecuente), se puede volver a habilitar mediante una opción de configuración (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>). No obstante, si el método Replace está activado, puede crear vulnerabilidades de seguridad y solo debería usarse tras una revisión exhaustiva.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|

