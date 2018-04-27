### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Los elementos DataTemplate de WPF ahora son visibles en la UIA

|   |   |
|---|---|
|Detalles|Anteriormente, los elementos <xref:System.Windows.DataTemplate?displayProperty=name> no eran visibles para la automatización de la interfaz de usuario. A partir de la versión 4.5, la automatización de la IU detectará estos elementos. Esto resulta útil en muchos casos, pero puede interrumpir las pruebas que dependan de árboles de la UIA que no contengan elementos <xref:System.Windows.DataTemplate?displayProperty=name>.|
|Sugerencia|Puede ser necesario actualizar las pruebas de automatización de la interfaz de usuario para esta aplicación con el fin de procesar el árbol de la UIA que ahora incluye elementos <xref:System.Windows.DataTemplate?displayProperty=name> que antes no eran visibles. Por ejemplo, en aquellas pruebas en las que se espere que haya ciertos elementos contiguos entre sí, ahora puede ser necesario esperar ciertos elementos intermedios de la UIA que antes no eran visibles. También puede ser necesario actualizar con nuevos valores pruebas que dependan de ciertos recuentos o índices para elementos de la UIA.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.DataTemplate.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)?displayProperty=nameWithType></li></ul>|

