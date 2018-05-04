### <a name="binding-a-wpf-selector-property-such-as-selecteditem-to-a-static-property-does-not-work"></a>No funciona el enlace de una propiedad de selector WPF (por ejemplo, "SelectedItem") a una propiedad estática

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, las propiedades del selector de WPF (como "SelectedItem" en <xref:System.Windows.Controls.ListBox?displayProperty=name> o <xref:System.Windows.Controls.DataGrid?displayProperty=name>) que están enlazadas a datos de propiedades estáticas no se actualizan correctamente cuando se actualiza su propiedad enlazada.|
|Sugerencia|Este comportamiento se revirtió en una actualización de servicio para .NET Framework 4.5. Para corregir este problema, actualice .NET Framework 4.5 o actualice a la versión 4.5.1 o posterior de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

