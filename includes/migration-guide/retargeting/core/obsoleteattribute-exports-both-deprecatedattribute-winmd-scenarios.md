### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute se exporta como ObsoleteAttribute y DeprecatedAttribute en escenarios de WinMD

|   |   |
|---|---|
|Detalles|Cuando se crea una biblioteca de metadatos de Windows (archivo .winmd), el atributo <xref:System.ObsoleteAttribute?displayProperty=name> se exporta como <xref:System.ObsoleteAttribute?displayProperty=name> y como [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).|
|Sugerencia|Volver a compilar el código fuente existente que usa el atributo <xref:System.ObsoleteAttribute?displayProperty=name> puede generar advertencias cuando ese código se usa desde C++/CX o JavaScript. No se recomienda aplicar <xref:System.ObsoleteAttribute?displayProperty=name> y [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al código en los ensamblados administrados; se podrían producir advertencias de compilación.|
|Ámbito|Borde|
|Versión|4.5.1|
|Tipo|Redestinación|

