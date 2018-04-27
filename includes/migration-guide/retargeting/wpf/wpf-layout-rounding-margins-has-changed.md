### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Ha cambiado el redondeo del diseño de márgenes en WPF

|   |   |
|---|---|
|Detalles|Ha cambiado la manera en la que se redondean los márgenes, así como los bordes y el fondo de estos. Debido a este cambio:<ul><li>El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.</li><li>La posición de un objeto se puede mover un píxel como máximo.</li><li>Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.</li></ul>De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.|
|Sugerencia|Como esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles de WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento si se agrega la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;</code>Las aplicaciones destinadas a .NET Framework 4.6 pero en las que se quiere representar los controles de WPF mediante el algoritmo de diseño anterior lo pueden hacer si se agrega la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;</code>.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|

