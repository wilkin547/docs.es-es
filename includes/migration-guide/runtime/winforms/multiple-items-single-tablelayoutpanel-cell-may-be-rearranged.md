### <a name="multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>Es posible reordenar varios elementos en una única celda TableLayoutPanel

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, si hay varios elementos colocados en la misma celda <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>, pueden aparecer en un orden diferente al de .NET Framework 4.0.|
|Sugerencia|Este comportamiento se revirtió en una actualización de servicio para .NET Framework 4.5. Para corregir este problema, actualice .NET Framework 4.5 o actualice a la versión 4.5.1 o posterior de .NET Framework. También puede evitarse el caso ambiguo de colocar varios elementos en la misma celda <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Forms.TableLayoutControlCollection.Add(System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32)?displayProperty=nameWithType></li></ul>|
|Analizadores|<ul><li>CD0098</li></ul>|

