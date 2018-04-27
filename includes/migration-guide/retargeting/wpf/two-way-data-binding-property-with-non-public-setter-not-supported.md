### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>No se admite el enlace de datos bidireccional a una propiedad con un establecedor no público

|   |   |
|---|---|
|Detalles|Nunca se ha admitido el escenario de tratar de enlazar datos a una propiedad sin establecedor público. A partir de .NET Framework 4.5.1, este escenario iniciará una excepción <xref:System.InvalidOperationException?displayProperty=name>. Tenga en cuenta que esta nueva excepción solo se iniciará para aquellas aplicaciones que tengan .NET Framework 4.5.1 como destino específico. Si una aplicación tiene como destino .NET Framework 4.5, se permitirá la llamada. Si la aplicación no tiene como destino ninguna versión concreta de .NET Framework, el enlace se tratará como unidireccional.|
|Sugerencia|Debería actualizarse la aplicación para utilizar un enlace bidireccional, o bien para exponer públicamente el establecedor de la propiedad. También es posible establecer .NET Framework 4.5 como destino para que la aplicación presente el comportamiento anterior.|
|Ámbito|Secundaria|
|Versión|4.5.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType></li></ul>|

