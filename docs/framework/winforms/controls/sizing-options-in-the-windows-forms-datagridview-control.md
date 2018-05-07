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
ms.openlocfilehash: 6e3a7786970ef536da4ef7628cd33ae067ba90be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView> filas, columnas y encabezados pueden cambiar tamaño causas muy distintas. En la tabla siguiente muestra estas causas.  
  
|Repetición|Descripción|  
|----------------|-----------------|  
|Cambio de tamaño de usuario|Los usuarios pueden realizar los ajustes de tamaño arrastrando o haciendo doble clic en los divisores de fila, columna o encabezado.|  
|Cambio de tamaño del control|En el modo de relleno de columna, los anchos de columna cambian cuando cambia el ancho del control; Por ejemplo, cuando se acopla el control a su elemento primario y el usuario cambia el tamaño del formulario.|  
|Cambio del valor de celda|En los modos de ajuste automático de tamaño basado en contenido, tamaños cambian para adaptarse nuevos valores de presentación.|  
|Llamada al método|Cambio de tamaño basado en contenido mediante programación permite realizar ajustes de tamaño oportunos basados en valores de celda en el momento de la llamada al método.|  
|Configuración de la propiedad|También puede establecer valores de ancho y alto específico.|  
  
 De forma predeterminada, el cambio de tamaño de usuario está habilitada, se deshabilita el ajuste automático de tamaño y se recortan los valores de las celdas que son más anchos que las columnas.  
  
 En la tabla siguiente se muestra escenarios que puede usar para ajustar el comportamiento predeterminado o usar opciones de tamaño concretas para lograr efectos determinados.  
  
|Escenario|Implementación|  
|--------------|--------------------|  
|Utilice el modo de relleno de columna para mostrar datos con tamaño similar en un número relativamente pequeño de columnas que ocupar todo el ancho del control sin mostrar la barra de desplazamiento horizontal.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Usar el modo de relleno de columna con mostrar valores de diferentes tamaños.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Inicializar los anchos de columna relativos estableciendo la columna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> propiedades o llamar al control <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> método después de rellenar el control con datos.|  
|Utilice el modo de relleno de columna con valores de importancia variable.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Establecer grandes <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> los valores de las columnas que siempre se deben mostrar algunos de sus datos o utilizar una opción de tamaño distinto de rellenar el modo columnas específicas.|  
|Usa el modo de relleno de columna para evitar que se muestre el fondo del control.|Establecer el <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> propiedad de la última columna a <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> y usar otras opciones de ajuste de tamaño de las otras columnas. Si las demás columnas utilizan en exceso el espacio disponible, establezca el <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> propiedad de la última columna.|  
|Mostrar una columna de ancho fijo, como un icono o una columna de identificador.|Establecer <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> a <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> y <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.False> para la columna. Inicializar su ancho estableciendo la <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> propiedad o llamar al control <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> método después de rellenar el control con datos.|  
|Ajustar el tamaño automáticamente cada vez que cambia el contenido de celda para evitar el recorte y optimizar el uso del espacio.|Establecer una propiedad de ajuste automático de tamaño en un valor que representa un modo de ajuste de tamaño basado en contenido. Para evitar una reducción del rendimiento cuando se trabaja con grandes cantidades de datos, utilice un modo de ajuste de tamaño que calcula las filas mostradas.|  
|Ajustar el tamaño para ajustarse a los valores de filas mostradas para evitar las penalizaciones del rendimiento cuando se trabaja con muchas filas.|Utilice los valores de enumeración de modo de ajuste adecuado con el cambio de tamaño automático o mediante programación. Para ajustar el tamaño para ajustarse a los valores de filas recién presentadas durante el desplazamiento, llamar a un método de cambio de tamaño en un <xref:System.Windows.Forms.DataGridView.Scroll> controlador de eventos. Para personalizar el usuario haga doble clic en el cambio de tamaño para que únicamente los valores de filas mostradas determinen los nuevos tamaños, llame a un método de cambio de tamaño un <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> o <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> controlador de eventos.|  
|Ajustar el tamaño para ajustar el contenido de la celda sólo a horas específicas para evitar las penalizaciones del rendimiento o para habilitar el cambio de tamaño de usuario.|Llamar a un método de cambio de tamaño basado en contenido en un controlador de eventos. Por ejemplo, use la <xref:System.Windows.Forms.DataGridView.DataBindingComplete> eventos para inicializar tamaños después del enlace y controlar la <xref:System.Windows.Forms.DataGridView.CellValidated> o <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventos para ajustar el tamaño para compensar las modificaciones del usuario o cambios en un origen de datos enlazado.|  
|Ajustar el alto de fila para el contenido de las celdas de varias líneas.|Asegúrese de que el ancho de las columnas es adecuado para mostrar párrafos de texto y usar el tamaño de fila basado en contenido automática o mediante programación para ajustar el alto. Asegúrese también de que las celdas con contenido de varias líneas se muestran con un <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> valor de estilo de la celda <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> Normalmente, usará un modo de ajuste de tamaño automático de columna para mantener los anchos de columna o establecerlos en los anchos concretos antes de que se ajusta el alto de las filas.|  
  
## <a name="resizing-with-the-mouse"></a>Cambio de tamaño con el Mouse  
 De forma predeterminada, los usuarios pueden cambiar filas, columnas y encabezados que no utilizan un modo de ajuste automático de tamaño en función de los valores de celda. Para impedir que los usuarios cambiar el tamaño con otros modos, como el modo de relleno de columna, establezca una o varias de las siguientes acciones <xref:System.Windows.Forms.DataGridView> propiedades:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 También puede impedir que los usuarios cambien el tamaño de filas o columnas individuales estableciendo sus <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> propiedades. De forma predeterminada, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valor de propiedad se basa en el <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> valor de propiedad para las columnas y la <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> valor de propiedad para las filas. Si se establece explícitamente <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.True> o <xref:System.Windows.Forms.DataGridViewTriState.False>, sin embargo, el valor especificado reemplaza el valor del control es para esa fila o columna. Establecer <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.NotSet> para restaurar la herencia.  
  
 Dado que <xref:System.Windows.Forms.DataGridViewTriState.NotSet> restaura la herencia del valor, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> propiedad nunca devolverá una <xref:System.Windows.Forms.DataGridViewTriState.NotSet> valor a menos que la fila o columna no se ha agregado a un <xref:System.Windows.Forms.DataGridView> control. Si necesita determinar si la <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> heredan el valor de propiedad de una fila o columna, examine su <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad. Si el <xref:System.Windows.Forms.DataGridViewElement.State%2A> valor incluye el <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> marca, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> no se hereda el valor de propiedad.  
  
## <a name="automatic-sizing"></a>Ajuste automático de tamaño  
 Hay dos tipos de ajuste automático de tamaño en el <xref:System.Windows.Forms.DataGridView> control: modo de relleno de columna y el ajuste automático de tamaño basado en contenido.  
  
 Modo de relleno de columna hace que las columnas visibles en el control para rellenar el ancho del área de presentación del control. Para obtener más información acerca de este modo, vea [modo de relleno de columna en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 También puede configurar filas, columnas y encabezados para que ajuste automáticamente su tamaño para adaptarlas a su contenido de la celda. En este caso, el ajuste de tamaño se produce cada vez que cambia el contenido de la celda.  
  
> [!NOTE]
>  Si se mantienen los valores de celda en una caché de datos personalizados utilizando el modo virtual, el ajuste automático de tamaño se produce cuando el usuario edita un valor de celda, pero no se produce cuando se modifica un valor almacenado en caché fuera de un <xref:System.Windows.Forms.DataGridView.CellValuePushed> controlador de eventos. En este caso, llame a la <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> método para forzar que el control para actualizar la presentación de celda y aplique los modos de ajuste automático de tamaño actual.  
  
 Si está habilitado el ajuste automático de tamaño basado en contenido sólo para una dimensión, es decir, para filas pero no en las columnas, o para columnas pero no para filas, y <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> también está habilitado, el tamaño de ajuste también se produce cuando cambia la otra dimensión. Por ejemplo, si las filas pero no en las columnas están configuradas para el ajuste automático de tamaño y <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> está habilitada, los usuarios pueden arrastrar divisores de columna para cambiar el ancho de una columna y alto de las filas se ajustará automáticamente para que el contenido de la celda se siga mostrando por completo.  
  
 Si configura filas y columnas para el ajuste automático de tamaño basado en contenido y <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> está habilitada, el <xref:System.Windows.Forms.DataGridView> control ajustará los tamaños cada vez que el contenido de la celda cambia y utilizará una proporción de alto y ancho de celda ideal cuando calcule nuevos tamaños.  
  
 Para configurar el modo de ajuste de tamaño para encabezados y filas y columnas que no invalidan el valor del control, establezca uno o varios de los siguientes <xref:System.Windows.Forms.DataGridView> propiedades:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Para reemplazar el modo de ajuste de tamaño de columna del control para una columna individual, establezca su <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> propiedad en un valor distinto de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. El modo de ajuste de tamaño de una columna realmente viene determinado por su <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> propiedad. El valor de esta propiedad se basa en la columna <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> valor de propiedad, a menos que ese valor es <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, en cuyo caso el control <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> heredan el valor.  
  
 Utilice contenidos cambio de tamaño automático con precaución cuando se trabaja con grandes cantidades de datos. Para evitar las penalizaciones del rendimiento, utilice los modos de ajuste automático de tamaño que calculan tamaños basándose sólo en las filas mostradas en lugar de analizar todas las filas en el control. Para obtener el máximo rendimiento, se carga el uso mediante programación el cambio de tamaño en su lugar, por lo que puede cambiar el tamaño en momentos determinados, como inmediatamente después de nuevos datos.  
  
 Modos de ajuste automático de tamaño basado en contenido no afectan a filas, columnas o encabezados que haya ocultado estableciendo la fila o columna <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> propiedad o el control <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> o <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> propiedades para `false`. Por ejemplo, si una columna está oculta después de tamaño se ajusta automáticamente para ajustarse a un valor de celda elevado, la columna oculta no cambiará su tamaño si se elimina la fila que contiene el valor de celda de gran tamaño. Ajuste automático de tamaño no se produce cuando cambia la visibilidad, por lo que cambiar la columna <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> propiedad volver a `true` no se fuerza para volver a calcular su tamaño según su contenido actual.  
  
 Cambio de tamaño basado en contenido mediante programación afecta a filas, columnas y encabezados sin tener en cuenta su visibilidad.  
  
## <a name="programmatic-resizing"></a>Cambiar el tamaño mediante programación  
 Cuando se deshabilita el ajuste automático de tamaño, puede establecer mediante programación el ancho o alto exacto de filas, columnas o encabezados a través de las siguientes propiedades:  
  
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
  
 Estos métodos cambiará el tamaño de filas, columnas o encabezados una vez en lugar de configurarlos para dar nuevo tamaño continua. Los nuevos tamaños se calculan automáticamente para mostrar el contenido de la celda sin recortes. Cuando se mediante programación cambiar el tamaño de las columnas que tienen <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> valores de propiedad de <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, sin embargo, los anchos calculados contenidos se usan para ajustar proporcionalmente la columna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> valores de propiedad y la columna realmente anchos son a continuación, calcula de acuerdo con estas nuevas proporciones para que todas las columnas de rellenar el área de presentación disponibles del control.  
  
 Cambiar el tamaño mediante programación es útil para evitar las penalizaciones del rendimiento con el cambio de tamaño continuo. También es útil proporcionar tamaños iniciales para encabezados, columnas y filas ajustables por el usuario y para el modo de relleno de columna.  
  
 Normalmente, llamará a los métodos de cambio de tamaño mediante programación a horas específicas. Por ejemplo, puede cambiar el tamaño mediante programación de los todas las columnas inmediatamente después de cargar los datos, o mediante programación puede cambiar el tamaño una fila concreta después de que se ha modificado un valor de celda en particular.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Personalizar el comportamiento de ajuste de tamaño basado en contenido  
 Puede personalizar comportamientos de ajuste de tamaño cuando se trabaja con derivada <xref:System.Windows.Forms.DataGridView> tipos de celda, fila y columna invalidando el <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, o <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> métodos o mediante una llamada a protegido sobrecargas de método de cambio de tamaño de una derivada <xref:System.Windows.Forms.DataGridView> control. Las sobrecargas del método de cambio de tamaño protegido están diseñadas para trabajar en pares para lograr una proporción de alto y ancho de celda ideal, evitando las celdas demasiado ancho o altas. Por ejemplo, si se llama a la `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> método y pase un valor de `false` para el <xref:System.Boolean> parámetro, la sobrecarga calculará los altos y anchos ideales para las celdas de la fila, pero ajustará el alto de fila solo. A continuación, debe llamar a la <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> método para ajustar los anchos de columna al ideal calculado.  
  
## <a name="content-based-sizing-options"></a>Opciones de ajuste de tamaño basado en contenido  
 Las enumeraciones utilizadas por métodos y propiedades de tamaño tienen valores similares para el ajuste de tamaño basado en contenido. Con estos valores, puede limitar qué celdas se utilizan para calcular los tamaños preferidos. Para todas las enumeraciones de ajuste de tamaño, los valores con nombres que hacen referencia a las celdas mostradas limitan los cálculos a las celdas de filas mostradas. Excluidas las filas es útil para evitar una reducción del rendimiento cuando se trabaja con una gran cantidad de filas. También puede restringir los cálculos a los valores de celda de las celdas con o sin encabezado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [Cambiar el tamaño de columnas y filas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Modo de relleno de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 [Establecer modos de cambio de tamaño para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
