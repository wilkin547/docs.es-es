---
title: "Opciones de ajuste de tama&#241;o en el control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadrículas de datos, ajustar el tamaño de las columnas"
  - "cuadrículas de datos, ajustar el tamaño de las filas"
  - "cuadrículas de datos, opciones de tamaño"
  - "DataGridView (control) [Windows Forms], ajustar el tamaño de las columnas"
  - "DataGridView (control) [Windows Forms], ajustar el tamaño de las filas"
  - "DataGridView (control) [Windows Forms], opciones de tamaño"
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Opciones de ajuste de tama&#241;o en el control DataGridView de formularios Windows Forms
Las filas, columnas y encabezados de <xref:System.Windows.Forms.DataGridView> pueden cambiar de tamaño por causas muy distintas.  La siguiente tabla muestra estas causas.  
  
|Causa|Descripción|  
|-----------|-----------------|  
|Cambio de tamaño por el usuario|Los usuarios pueden realizar ajustes de tamaño arrastrando o haciendo doble clic en divisores de fila, columna o encabezado.|  
|Cambio de tamaño de los controles|En una columna en modo de relleno, los anchos de columna cambian cuando el ancho del control cambia; por ejemplo, cuando se acopla un control a su elemento primario y el usuario cambia el tamaño del formulario.|  
|Cambio de un valor de celda|En los modos de ajuste automático del tamaño basado en contenido, los tamaños cambian para adaptarse a los nuevos valores de presentación.|  
|Llamada a método|El cambio de tamaño basado en contenido mediante programación permite realizar ajustes de tamaño oportunos basándose en valores de celda en el momento de la llamada al método.|  
|Valor de propiedades|También puede establecer valores de alto y ancho concretos.|  
  
 De forma predeterminada, está habilitado el cambio de tamaño por el usuario, está deshabilitado el tamaño automático y se recortan los valores de celda que son más anchos que sus columnas.  
  
 En la tabla siguiente se muestran escenarios que puede utilizar para ajustar el comportamiento predeterminado o para utilizar opciones de tamaño concretas con el fin de lograr efectos determinados.  
  
|Escenario|Implementación|  
|---------------|--------------------|  
|Utilice el modo de relleno de columna para mostrar datos con tamaño similar en un número de columnas relativamente pequeño que ocupan el ancho completo del control sin mostrar la barra de desplazamiento horizontal.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>.|  
|Utilice el modo de relleno de columna con valores de presentación de tamaños variables.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>.  Inicialice los anchos de columna relativos estableciendo las propiedades <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de  columna o llamando al método <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> del control después de rellenar el control con datos.|  
|Utilice el modo de relleno de columna con valores de importancia variable.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>.  Establezca valores de <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> elevados para columnas que deben mostrar siempre algunos de los datos o utilice una opción de tamaño que no sea el modo de relleno para columnas concretas.|  
|Utilice el modo de relleno de columna para evitar que se muestre el fondo del control.|Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> de la última columna en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> y utilice otras opciones de tamaño para las otras columnas.  Si las demás columnas utilizan en exceso el espacio disponible, establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> de la última columna.|  
|Muestre una columna de ancho fijo, como un icono o un Id. de columna.|Establezca <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> y <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> en <xref:System.Windows.Forms.DataGridViewTriState> para la columna.  Para inicializar el ancho establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> o llame al método <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> del control después de rellenar el control con datos.|  
|Ajuste tamaños automáticamente cada vez que cambia el contenido de la celda para evitar el recorte y optimizar el uso de espacio.|Establezca una propiedad de tamaño automático en un valor que representa un modo de tamaño basado en contenido.  Para evitar una reducción del rendimiento al trabajar con grandes volúmenes de datos, utilice un modo de tamaño que sólo calcule las filas mostradas.|  
|Ajuste tamaños para encajar los valores en las filas mostradas con el fin de impedir reducciones del rendimiento al trabajar con muchas filas.|Utilice los valores de enumeración del modo de tamaño adecuados con el cambio de tamaño automático o mediante programación.  Para ajustar tamaños con el fin de adaptar valores de filas recién presentadas cuando se desplaza, llame a un método de cambio de tamaño en un controlador de eventos <xref:System.Windows.Forms.DataGridView.Scroll>.  Para personalizar el cambio de tamaño con doble clic por parte del usuario de modo que sólo los valores de las filas mostradas determinen los nuevos tamaños, llame al método de cambio de tamaño de un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> o <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick>.|  
|Ajuste tamaños para adaptar el contenido de la celda sólo en momentos concretos con el fin de impedir las reducciones del rendimiento o para habilitar el cambio de tamaño por parte del usuario.|Llame a un método de cambio de tamaño basado en contenido en un controlador de eventos.  Por ejemplo, utilice el evento <xref:System.Windows.Forms.DataGridView.DataBindingComplete> para inicializar tamaños después del enlace y controlar el evento <xref:System.Windows.Forms.DataGridView.CellValidated> o <xref:System.Windows.Forms.DataGridView.CellValueChanged> para ajustar tamaños con el fin de compensar las modificaciones o cambios del usuario en un origen de datos enlazado.|  
|Ajuste los altos de fila para el contenido de celdas de varias líneas.|Garantice que los anchos de columna son adecuados para mostrar párrafos de texto y utilice el tamaño de fila automático o basado en contenido para ajustar los altos.  También garantice que se muestran las celdas con contenido de varias líneas utilizando un valor de estilo de celda <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> de <xref:System.Windows.Forms.DataGridViewTriState>.<br /><br /> Normalmente, utilizará un modo de tamaño automático de columna para mantener los anchos de columna o establecerlos en los anchos concretos antes de que se ajusten los altos de fila.|  
  
## Cambiar el tamaño con el mouse  
 De forma predeterminada, los usuarios pueden cambiar el tamaño de filas, columnas y encabezados que no utilizan un modo de tamaño automático basado en valores de celda.  Para impedir que los usuarios cambien el tamaño con otros modos, como el modo de relleno de columna, establezca una o varias propiedades del control <xref:System.Windows.Forms.DataGridView> siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 También puede evitar que los usuarios cambien el tamaño de filas o columnas individuales estableciendo sus propiedades <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>.  De forma predeterminada, el valor de propiedad <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> se basa en el valor de propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> para columnas y el valor de propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> para filas.  Si establece explícitamente <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> en <xref:System.Windows.Forms.DataGridViewTriState> o <xref:System.Windows.Forms.DataGridViewTriState>, sin embargo, el valor especificado reemplaza al valor de control que es para esa fila o columna.  Establezca <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> en <xref:System.Windows.Forms.DataGridViewTriState> para restaurar la herencia.  
  
 Dado que <xref:System.Windows.Forms.DataGridViewTriState> restaura la herencia de valores, la propiedad <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> nunca devolverá un valor <xref:System.Windows.Forms.DataGridViewTriState> a no ser que no se haya agregado la fila o columna a un control <xref:System.Windows.Forms.DataGridView>.  Si necesita determinar si se hereda el valor de propiedad <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> de una fila o columna, examine la propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A>.  Si el valor <xref:System.Windows.Forms.DataGridViewElement.State%2A> incluye la marca <xref:System.Windows.Forms.DataGridViewElementStates>, no se heredará el valor de propiedad <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>.  
  
## Tamaño automático  
 Hay dos tipos de tamaño automático en el control <xref:System.Windows.Forms.DataGridView>: el modo de relleno de columna y el ajuste automático del tamaño basado en contenido.  
  
 El modo de relleno de columna hace que las columnas visibles del control rellenen el ancho del área de presentación del control.  Para obtener más información sobre este modo, vea [Modo de relleno de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 También puede configurar filas, columnas y encabezados para que ajusten automáticamente el tamaño con el fin de adaptarlo al contenido de la celda.  En este caso, el ajuste de tamaño se produce cada vez que cambia el contenido de la celda.  
  
> [!NOTE]
>  Si mantiene valores de celda en una caché de datos personalizada con el modo virtual, se produce el ajuste de tamaño automático cuando el usuario modifica un valor de celda pero no cuando altera un valor almacenado en memoria caché fuera de un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValuePushed>.  En este caso, llame al método <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> para forzar que el control actualice la presentación de celda y aplique los modos de tamaño automático actuales.  
  
 Si el ajuste automático del tamaño basado en contenido está habilitado sólo para una dimensión, es decir, para filas pero no para columnas o para columnas pero no para filas, y también está habilitado <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>, también se produce el ajuste de tamaño cada vez que cambia la otra dimensión.  Por ejemplo, si se configuran las filas pero no las columnas para el ajuste de tamaño automático y está habilitado <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>, los usuarios pueden arrastrar los divisores de columna para cambiar el ancho de una columna y se ajustarán automáticamente los altos de fila de modo que el contenido de la celda se siga mostrando por completo.  
  
 Si configura filas y columnas para el ajuste automático del tamaño basado en contenido y está habilitado <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>, el control <xref:System.Windows.Forms.DataGridView> ajustará los tamaños cada vez que se modifique el contenido de la celda y utilizará una relación de alto con ancho de celda cuando calcule nuevos tamaños.  
  
 Para configurar el modo de tamaño para encabezados y filas y para columnas que no reemplazan el valor de control, establezca una o varias de las propiedades de <xref:System.Windows.Forms.DataGridView> siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Para reemplazar el modo de tamaño de columna del control para una columna individual, establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> en un valor distinto de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.  Su propiedad <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> determina realmente el modo de tamaño de una columna.  El valor de esta propiedad se basa en el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> de la columna a no ser que el valor sea <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>, en cuyo caso se heredará el valor <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> del control.  
  
 Utilice con precaución el cambio de tamaño automático basado en contenido cuando trabaje con grandes volúmenes de datos.  Para impedir una reducción del rendimiento, utilice los modos de tamaño automático que calculan tamaños basándose sólo en las filas mostradas en lugar de analizar todas las filas del control.  Para obtener un rendimiento máximo, utilice en su lugar el cambio de tamaño mediante programación para que pueda cambiar el tamaño en momentos concretos, como inmediatamente después de que se cargan los nuevos datos.  
  
 Los modos de ajuste automático del tamaño basado en contenido no afectan a filas, columnas o encabezados que haya ocultado estableciendo la propiedad <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> de fila o columna o las propiedades <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> o <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> del control en `false`.  Por ejemplo, si se oculta una columna después de que se ajusta automáticamente el tamaño para adaptarse a un valor de celda elevado, la columna oculta no cambiará el tamaño si se elimina la fila que contiene el valor de celda elevado.  El tamaño automático no se produce cuando cambia la visibilidad, de modo que al cambiar la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> de la columna de nuevo a `true` no se forzará que se vuelva a calcular su tamaño basándose en el contenido actual.  
  
 El cambio de tamaño mediante programación basado en contenido afecta a filas, columnas y encabezados sin tener en cuenta su visibilidad.  
  
## Cambio de tamaño mediante programación  
 Cuando se deshabilita el tamaño automático, puede establecer mediante programación el ancho o alto exacto de filas, columnas o encabezados a través de las propiedades siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>  
  
 También puede cambiar mediante programación el tamaño de filas, columnas y encabezados para ajustar su contenido con los métodos siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Estos métodos cambiarán el tamaño de filas, columnas o encabezados una vez en lugar de configurarlos para el cambio de tamaño continuo.  Los nuevos tamaños se calculan automáticamente para mostrar todo el contenido de las celdas sin recortar.  Cuando cambia el tamaño mediante programación de las columnas que tienen valores de propiedad <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>, no obstante, se utilizan los anchos basados en contenido calculados para ajustar de forma proporcional los valores de propiedad <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de la columna y los anchos de columna se calculan realmente según estas nuevas proporciones de modo que todas las columnas rellenen el área de presentación disponible del control.  
  
 El cambio de tamaño mediante programación resulta de utilidad para evitar las reducciones del rendimiento con el cambio continuo de tamaño.  También resulta de utilidad para proporcionar tamaños iniciales a filas, columnas y encabezados de cambio de tamaño por el usuario y al modo de relleno de columna.  
  
 Llamará normalmente a los métodos de cambio de tamaño mediante programación en momentos concretos.  Por ejemplo, podría cambiar mediante programación el tamaño de todas las columnas inmediatamente después de cargar datos o de una fila concreta después de que se haya modificado un valor de celda concreto.  
  
## Personalizar el comportamiento del tamaño basado en contenido  
 Puede personalizar los comportamientos del tamaño cuando trabaja con tipos de celda, fila y columna de <xref:System.Windows.Forms.DataGridView> derivados reemplazando los métodos <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=fullName>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=fullName> o llamando a sobrecargas de método de cambio de tamaño protegido en un control <xref:System.Windows.Forms.DataGridView> derivado.  Las sobrecargas de método de cambio de tamaño protegido están diseñadas para trabajar en pares con el fin de lograr una relación de alto y ancho de celda ideal, lo que impide que haya celdas demasiado anchas o altas.  Por ejemplo, si llama a la sobrecarga `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` del método <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> y pasa un valor de `false` en el parámetro <xref:System.Boolean>, la sobrecarga calculará los altos y anchos ideales de las celdas de la fila, pero ajustará sólo los altos de fila.  Debe llamar a continuación al método <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> para ajustar los anchos de columna al ideal calculado.  
  
## Opciones de tamaño basado en contenido  
 Las enumeraciones que las propiedades y métodos de ajuste de tamaño utilizan tienen valores similares para el ajuste de tamaño basado en contenido.  Con estos valores, puede limitar qué celdas se utilizarán para calcular los tamaños preferidos.  Para todas las enumeraciones de tamaño, los valores con nombres que hacen referencia a las celdas mostradas limitan los cálculos a celdas de filas mostradas.  Cuando se trabaja con un gran volumen de filas resulta de utilidad excluir filas con el fin de impedir una reducción del rendimiento.  También puede restringir los cálculos a los valores de celda en celdas con o sin encabezado.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>   
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>   
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>   
 [Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)   
 [Modo de relleno de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer modos de cambio de tamaño para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)