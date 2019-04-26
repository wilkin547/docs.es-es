---
title: Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: 2f76bbca3d4b6e642c0eec2129c4a2abee752655
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903167"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView> encabezados, columnas y filas pueden cambiar el tamaño causas muy distintas. En la tabla siguiente muestra estas causas.  
  
|aparición|Descripción|  
|----------------|-----------------|  
|Cambio de tamaño de usuario|Los usuarios pueden realizar ajustes de tamaño arrastrando o haga doble clic en los divisores de fila, columna o encabezado.|  
|Cambio de tamaño de control|En el modo de relleno de columna, cambian los anchos de columna cuando se cambia el ancho del control; Por ejemplo, cuando está acoplado el control a su elemento primario y el usuario cambia el tamaño del formulario.|  
|Cambio del valor de celda|En los modos de ajuste de tamaño automático basado en contenido, los tamaños de cambian para ajustarse a los nuevos valores de presentación.|  
|Llamada al método|Cambio de tamaño basado en contenido mediante programación le permite realizar ajustes de tamaño oportunos según los valores de celda en el momento de la llamada al método.|  
|Configuración de la propiedad|También puede establecer valores de ancho y alto específico.|  
  
 De forma predeterminada, el cambio de tamaño de usuario está habilitado, se deshabilita el ajuste de tamaño automático y se recortan los valores de celda que sean más anchos que las columnas.  
  
 En la tabla siguiente se muestra los escenarios que puede usar para ajustar el comportamiento predeterminado o para usar opciones de ajuste de tamaño específico para lograr efectos determinados.  
  
|Escenario|Implementación|  
|--------------|--------------------|  
|Utilice el modo de relleno de columna para mostrar datos con tamaño similar en un número relativamente pequeño de columnas que ocupa todo el ancho del control sin mostrar la barra de desplazamiento horizontal.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Usar el modo de relleno de columna con mostrar los valores de distintos tamaños.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Inicializar los anchos de columna relativos estableciendo la columna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> propiedades o mediante una llamada del control <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> método después de rellenar el control con datos.|  
|Utilice el modo de relleno de columna con valores de importancia variable.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Establecer grandes <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> los valores de modo para las columnas específicas de relleno de columnas que siempre se deben mostrar algunos de sus datos o usar una opción de ajuste de tamaño distinto.|  
|Utilice el modo de relleno de columna para evitar que se muestre el fondo del control.|Establecer el <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> propiedad de la última columna a <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> y usar otras opciones de ajuste de tamaño de las otras columnas. Si las demás columnas use gran cantidad de espacio disponible, establezca el <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> propiedad de la última columna.|  
|Mostrar una columna de ancho fijo, como un icono o una columna de identificador.|Establecer <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> a <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> y <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.False> para la columna. Inicializar su ancho estableciendo el <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> propiedad o mediante una llamada del control <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> método después de rellenar el control con datos.|  
|Ajustar automáticamente los tamaños cada vez que cambie de contenido de la celda para evitar el recorte y optimizar el uso del espacio.|Establecer una propiedad de tamaño automático en un valor que representa un modo de ajuste de tamaño basado en contenido. Para evitar una reducción del rendimiento cuando se trabaja con grandes cantidades de datos, utilice un modo de ajuste de tamaño que calcula solo las filas mostradas.|  
|Ajustar el tamaño para ajustarse a los valores en filas mostradas para evitar penalizaciones de rendimiento cuando se trabaja con muchas filas.|Use los valores de enumeración de modo de ajuste de tamaño adecuado con el cambio de tamaño automático o mediante programación. Para ajustar los tamaños para ajustar los valores en las filas recién mostradas al desplazarse, llamar a un método de cambio de tamaño en un <xref:System.Windows.Forms.DataGridView.Scroll> controlador de eventos. Para personalizar el usuario haga doble clic en el cambio de tamaño para que solo los valores de filas mostradas determinan los nuevos tamaños, llamar a un método de cambio de tamaño en un <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> o <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> controlador de eventos.|  
|Ajustar el tamaño para ajustar el contenido de celda solo a horas específicas para evitar las penalizaciones de rendimiento o para habilitar el cambio de tamaño de usuario.|Llamar a un método de cambio de tamaño basado en contenido en un controlador de eventos. Por ejemplo, use el <xref:System.Windows.Forms.DataGridView.DataBindingComplete> eventos para inicializar tamaños después del enlace y controlar el <xref:System.Windows.Forms.DataGridView.CellValidated> o <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventos para ajustar el tamaño para compensar las modificaciones del usuario o los cambios en un origen de datos.|  
|Ajustar el alto de fila de contenido de la celda de varias líneas.|Asegúrese de que los anchos de columna son adecuados para mostrar párrafos de texto y utilizar el tamaño de fila basado en contenido automática o mediante programación para ajustar el alto. Asegúrese también de que las celdas con contenido de varias líneas se muestran con un <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> valor de estilo de celda <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> Normalmente, usará un modo de ajuste de tamaño automático de columna para mantener los anchos de columna o establecerlos en los anchos concretos antes de que se ajuste el alto de fila.|  
  
## <a name="resizing-with-the-mouse"></a>Cambio de tamaño con el Mouse  
 De forma predeterminada, los usuarios pueden cambiar el tamaño de filas, columnas y encabezados que no usan un modo de ajuste de tamaño automático basado en valores de celda. Para evitar que los usuarios cambien el tamaño con otros modos, como el modo de relleno de columna, establezca uno o varios de los siguientes <xref:System.Windows.Forms.DataGridView> propiedades:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 También puede evitar que los usuarios cambien el tamaño de filas o columnas individuales estableciendo sus <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> propiedades. De forma predeterminada, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> el valor de propiedad se basa en el <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> valor de propiedad para las columnas y la <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> valor de propiedad para las filas. Si se establece explícitamente <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.True> o <xref:System.Windows.Forms.DataGridViewTriState.False>, sin embargo, las invalidaciones del valor especificado es el valor de control para esa fila o columna. Establecer <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.NotSet> para restaurar la herencia.  
  
 Dado que <xref:System.Windows.Forms.DataGridViewTriState.NotSet> restaura la herencia del valor, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> propiedad nunca devolverá un <xref:System.Windows.Forms.DataGridViewTriState.NotSet> valor a menos que la fila o columna no se agregó a una <xref:System.Windows.Forms.DataGridView> control. Si necesita determinar si el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> se hereda el valor de propiedad de una fila o columna, examine su <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad. Si el <xref:System.Windows.Forms.DataGridViewElement.State%2A> valor incluye el <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> marca, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> no se hereda el valor de propiedad.  
  
## <a name="automatic-sizing"></a>Ajuste de tamaño automático  
 Hay dos tipos de cambio de tamaño automático en el <xref:System.Windows.Forms.DataGridView> control: modo de relleno de columna y el ajuste de tamaño automático basado en contenido.  
  
 Modo de relleno de columna hace que las columnas visibles en el control para rellenar el ancho del área de presentación del control. Para obtener más información acerca de este modo, consulte [modo de relleno de columna en el DataGridView Control de formularios de Windows](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 También puede configurar las filas, columnas y encabezados para ajustar automáticamente su tamaño para ajustarse a su contenido de la celda. En este caso, el ajuste de tamaño se produce cada vez que cambia el contenido de la celda.  
  
> [!NOTE]
>  Si mantiene los valores de celda en una caché de datos personalizados utilizando el modo virtual, ajuste de tamaño automático se produce cuando el usuario edita un valor de celda, pero no se produce cuando se modifica un valor almacenado en caché fuera de un <xref:System.Windows.Forms.DataGridView.CellValuePushed> controlador de eventos. En este caso, llame a la <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> método para forzar que el control para actualizar la presentación de la celda y aplique los modos de ajuste automático del tamaño actual.  
  
 Si está habilitado el ajuste de tamaño automático basado en contenido sólo para una dimensión, es decir, para las filas, pero no en las columnas, o para las columnas pero no las filas, y <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> también está habilitada, el tamaño de ajuste también se produce cuando cambia la otra dimensión. Por ejemplo, si las filas, pero no en las columnas están configuradas para el ajuste de tamaño automático y <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> está habilitado, los usuarios pueden arrastrar los divisores de columna para cambiar el ancho de una columna y alto de las filas se ajustará automáticamente para que el contenido de la celda sigue totalmente se muestra.  
  
 Si configura las filas y columnas para el ajuste de tamaño automático basado en contenido y <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> está habilitada, el <xref:System.Windows.Forms.DataGridView> control ajustará los tamaños cada vez que el contenido de la celda cambió y usará una proporción de alto y ancho de celda ideal al calcular los nuevos tamaños.  
  
 Para configurar el modo de ajuste de tamaño para los encabezados y las filas y columnas que no invalidan el valor del control, establezca uno o varios de los siguientes <xref:System.Windows.Forms.DataGridView> propiedades:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Para reemplazar el modo de ajuste de tamaño de columna del control de una columna individual, establezca su <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> propiedad a un valor distinto de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. El modo de ajuste para una columna realmente viene determinada por su <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> propiedad. El valor de esta propiedad se basa en la columna <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> valor a menos que ese valor de la propiedad <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, en cuyo caso el control <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> se hereda el valor.  
  
 Utilice basado en contenido cambio de tamaño automático con precaución cuando se trabaja con grandes cantidades de datos. Para evitar las penalizaciones de rendimiento, utilice los modos de ajuste de tamaño automático que calcule los tamaños basándose únicamente en las filas mostradas en lugar de analizar todas las filas del control. Para obtener el máximo rendimiento, se carga el uso mediante programación el cambio de tamaño en su lugar para que puede cambiar el tamaño en momentos específicos, como inmediatamente después de nuevos datos.  
  
 Modos de tamaño automático basado en contenido no afectan a las filas, columnas o los encabezados que haya ocultado estableciendo la fila o columna <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> propiedad o el control <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> o <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> propiedades a `false`. Por ejemplo, si una columna se oculta una vez que tamaño se ajusta automáticamente para ajustarse a un valor de celda de gran tamaño, la columna oculta no cambiará su tamaño si se elimina la fila que contiene el valor de celda de gran tamaño. Ajuste de tamaño automático no se produce cuando cambia la visibilidad, así que si cambia la columna <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> propiedad nuevo a `true` no lo obliga a volver a calcular su tamaño en función de su contenido actual.  
  
 Cambio de tamaño basado en contenido mediante programación afecta a las filas, columnas y encabezados, independientemente de su visibilidad.  
  
## <a name="programmatic-resizing"></a>El cambio de tamaño mediante programación  
 Cuando se deshabilita el ajuste de tamaño automático, puede establecer mediante programación el ancho o alto exacto de filas, columnas o encabezados a través de las siguientes propiedades:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Mediante programación puede cambiar el tamaño de filas, columnas y encabezados para ajustar su contenido mediante los métodos siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Estos métodos cambiará de tamaño de filas, columnas, o los encabezados una vez en lugar de configurarlos para cambiar el tamaño de continua. Los nuevos tamaños se calculan automáticamente para mostrar todo el contenido de celda sin recortes. Cuando se mediante programación cambiar el tamaño de las columnas que tienen <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> valores de propiedad de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, sin embargo, los anchos calculados basada en contenidos se usan para ajustar proporcionalmente la columna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> valores de propiedad y la columna realmente es de ancho a continuación, calcula de acuerdo con estas proporciones nuevo para que todas las columnas rellenen el área de presentación disponibles del control.  
  
 El cambio de tamaño mediante programación es útil para evitar las penalizaciones de rendimiento con el cambio de tamaño continua. También es útil proporcionar tamaños iniciales para encabezados, columnas y filas ajustables por el usuario y para el modo de relleno de columna.  
  
 Normalmente, llamará a los métodos de cambio de tamaño mediante programación a horas específicas. Por ejemplo, mediante programación podría cambiar el tamaño todas las columnas inmediatamente después de cargar datos, o mediante programación podría cambiar el tamaño una determinada fila una vez que se ha modificado un valor de celda en particular.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Personalizar el comportamiento de ajuste de tamaño basado en contenido  
 Puede personalizar los comportamientos de ajuste de tamaño cuando se trabaja con derivada <xref:System.Windows.Forms.DataGridView> tipos de celda, fila y columna invalidando el <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, o <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> métodos o mediante una llamada a protegido el cambio de tamaño las sobrecargas de método en un derivado <xref:System.Windows.Forms.DataGridView> control. Las sobrecargas del método de cambio de tamaño protegido están diseñadas para funcionar en pares para lograr una relación de alto y ancho de celda ideal, evitando celdas demasiado anchas o altas. Por ejemplo, si se llama a la `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> método y pase un valor de `false` para el <xref:System.Boolean> parámetro, la sobrecarga calculará los altos y anchos ideales para las celdas de la fila, pero se ajustará el alto de fila solo. A continuación, debe llamar a la <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> método para ajustar los anchos de columna al ideal calculado.  
  
## <a name="content-based-sizing-options"></a>Opciones de ajuste de tamaño basado en contenido  
 Las enumeraciones utilizadas por los métodos y propiedades de tamaño tienen valores similares para el ajuste de tamaño basado en contenido. Con estos valores, puede limitar qué celdas se usan para calcular los tamaños preferidos. Para todas las enumeraciones de ajuste de tamaño, los valores con nombres que hacen referencia a las celdas mostradas limitan sus cálculos de celdas en filas mostradas. Son útil para evitar una reducción del rendimiento cuando se trabaja con una gran cantidad de filas excluidas las filas. También puede restringir los cálculos a los valores de celda de las celdas con o sin encabezado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Cambiar el tamaño de columnas y filas en el control DataGridView de Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Modo de relleno de columnas en el control DataGridView de formularios Windows Forms](column-fill-mode-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer modos de ajuste de tamaño del Control DataGridView de formularios Windows Forms](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
