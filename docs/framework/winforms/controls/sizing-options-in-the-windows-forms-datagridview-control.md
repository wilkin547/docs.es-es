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
ms.openlocfilehash: a8e2e05877746dfb043b7e8ac2a6c2b7017883c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960418"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView>las filas, columnas y encabezados pueden cambiar el tamaño como resultado de muchas repeticiones diferentes. En la tabla siguiente se muestran estas repeticiones.  
  
|Casos|DESCRIPCIÓN|  
|----------------|-----------------|  
|Cambiar el tamaño del usuario|Los usuarios pueden realizar ajustes de tamaño arrastrando o haciendo doble clic en los divisores de fila, columna o encabezado.|  
|Cambiar el tamaño del control|En el modo de relleno de columna, los anchos de columna cambian cuando cambia el ancho del control; por ejemplo, cuando el control está acoplado a su formulario primario y el usuario cambia el tamaño del formulario.|  
|Cambio de valor de celda|En los modos de ajuste automático de tamaño basados en contenido, los tamaños cambian para ajustarse a los nuevos valores de presentación.|  
|Llamada al método|El cambio de tamaño basado en contenido mediante programación permite realizar ajustes de tamaño oportunista basados en valores de celda en el momento de la llamada al método.|  
|Configuración de la propiedad|También puede establecer valores específicos de alto y ancho.|  
  
 De forma predeterminada, el cambio de tamaño de usuario está habilitado, el ajuste de tamaño automático está deshabilitado y los valores de celda más anchos que sus columnas se recortan.  
  
 En la tabla siguiente se muestran los escenarios que puede usar para ajustar el comportamiento predeterminado o para usar opciones de tamaño específicas para lograr efectos concretos.  
  
|Escenario|Implementación|  
|--------------|--------------------|  
|Use el modo de relleno de columnas para Mostrar datos de tamaño similar en un número relativamente pequeño de columnas que ocupan todo el ancho del control sin mostrar la barra de desplazamiento horizontal.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Use el modo de relleno de columnas con valores de presentación de tamaños variables.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Inicialice los anchos de columna relativos estableciendo las <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> propiedades de columna o llamando al <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> método de control después de llenar el control con datos.|  
|Use el modo de relleno de columnas con valores de importancia variable.|Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Establezca valores <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> grandes para las columnas que siempre deben mostrar algunos de los datos o usar una opción de ajuste de tamaño distinta del modo de relleno para columnas específicas.|  
|Use el modo de relleno de columna para evitar que se muestre el fondo del control.|Establezca la <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> propiedad de la última columna en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> y use otras opciones de ajuste de tamaño para las demás columnas. Si las demás columnas utilizan demasiado espacio disponible, establezca la <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> propiedad de la última columna.|  
|Mostrar una columna de ancho fijo, como un icono o una columna de identificador.|Establezca <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> y <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> en paralacolumna.<xref:System.Windows.Forms.DataGridViewTriState.False> Inicialice su ancho estableciendo la <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> propiedad o llamando al método de control <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> después de llenar el control con datos.|  
|Ajuste los tamaños automáticamente cada vez que cambie el contenido de la celda para evitar el recorte y optimizar el uso del espacio.|Establezca una propiedad de ajuste de tamaño automática en un valor que represente un modo de ajuste de tamaño basado en contenido. Para evitar una reducción del rendimiento al trabajar con grandes cantidades de datos, use un modo de ajuste de tamaño que solo calcule las filas mostradas.|  
|Ajuste los tamaños para ajustar los valores de las filas mostradas para evitar las penalizaciones de rendimiento al trabajar con muchas filas.|Utilice los valores de enumeración de modo de ajuste de tamaño adecuados con el cambio de tamaño automático o mediante programación. Para ajustar los tamaños de modo que se ajusten a los valores de las filas que se muestran recientemente mientras <xref:System.Windows.Forms.DataGridView.Scroll> se desplaza, llame a un método de cambio de tamaño en un controlador de eventos. Para personalizar el cambio de tamaño del usuario, de modo que solo los valores de las filas mostradas determinen los nuevos tamaños, <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> llame <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> a un método de cambio de tamaño en un controlador de eventos o.|  
|Ajuste los tamaños para ajustar el contenido de la celda solo en momentos concretos para evitar penalizaciones de rendimiento o para habilitar el cambio de tamaño del usuario.|Llame a un método de cambio de tamaño basado en contenido en un controlador de eventos. Por ejemplo, use el <xref:System.Windows.Forms.DataGridView.DataBindingComplete> evento para inicializar los tamaños después del enlace y <xref:System.Windows.Forms.DataGridView.CellValidated> controle el evento o <xref:System.Windows.Forms.DataGridView.CellValueChanged> para ajustar los tamaños para compensar las modificaciones o los cambios de usuario en un origen de datos enlazado.|  
|Ajuste el alto de las filas para el contenido de las celdas de varias líneas.|Asegúrese de que los anchos de columna son adecuados para mostrar párrafos de texto y usar el ajuste de tamaño de fila basado en contenido automático o mediante programación para ajustar el alto. Asegúrese también de que las celdas con contenido de varias líneas <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> se muestran utilizando un <xref:System.Windows.Forms.DataGridViewTriState.True>valor de estilo de celda de.<br /><br /> Normalmente, usará un modo de ajuste de tamaño de columna automático para mantener los anchos de columna o establecerlos en anchos específicos antes de que se ajuste el alto de las filas.|  
  
## <a name="resizing-with-the-mouse"></a>Cambiar el tamaño con el mouse  
 De forma predeterminada, los usuarios pueden cambiar el tamaño de filas, columnas y encabezados que no usan un modo de ajuste de tamaño automático basado en valores de celda. Para evitar que los usuarios cambien el tamaño con otros modos, como el modo de relleno de columnas, establezca una <xref:System.Windows.Forms.DataGridView> o varias de las propiedades siguientes:  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 También puede impedir que los usuarios cambien el tamaño de las filas o columnas <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> individuales estableciendo sus propiedades. De forma predeterminada, <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> el valor de la propiedad se <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> basa en el valor de la <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> propiedad para las columnas y el valor de la propiedad para las filas. Si se establece <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> explícitamente <xref:System.Windows.Forms.DataGridViewTriState.True> en <xref:System.Windows.Forms.DataGridViewTriState.False>o, sin embargo, el valor especificado invalida el valor del control para esa fila o columna. Establezca <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> en<xref:System.Windows.Forms.DataGridViewTriState.NotSet> para restaurar la herencia.  
  
 Dado <xref:System.Windows.Forms.DataGridViewTriState.NotSet> que restaura la herencia de valores, la <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> propiedad nunca devolverá <xref:System.Windows.Forms.DataGridViewTriState.NotSet> un valor a menos que la fila o columna no se haya <xref:System.Windows.Forms.DataGridView> agregado a un control. Si necesita determinar si el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valor de propiedad de una fila o columna es heredado, examine su <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad. Si el <xref:System.Windows.Forms.DataGridViewElement.State%2A> valor incluye la <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> marca, el <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valor de la propiedad no se hereda.  
  
## <a name="automatic-sizing"></a>Ajuste automático de tamaño  
 Hay dos tipos de ajuste automático de tamaño en <xref:System.Windows.Forms.DataGridView> el control: el modo de relleno de columnas y el ajuste automático de tamaño basado en contenido.  
  
 El modo de relleno de columnas hace que las columnas visibles del control rellenen el ancho del área de presentación del control. Para obtener más información sobre este modo, vea [el modo de relleno de columnas en el control DataGridView de Windows Forms](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 También puede configurar filas, columnas y encabezados para ajustar automáticamente sus tamaños para ajustarse al contenido de las celdas. En este caso, el ajuste de tamaño se produce cada vez que cambia el contenido de la celda.  
  
> [!NOTE]
> Si mantiene los valores de celda en una memoria caché de datos personalizada mediante el modo virtual, el ajuste de tamaño automático se produce cuando el usuario edita un valor de celda, pero no se produce cuando <xref:System.Windows.Forms.DataGridView.CellValuePushed> se modifica un valor almacenado en caché fuera de un controlador de eventos. En este caso, llame <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> al método para forzar que el control actualice la presentación de la celda y aplique los modos de ajuste automático de tamaño actuales.  
  
 Si el ajuste automático de tamaño basado en contenido está habilitado solo para una dimensión (es decir, para las filas pero no para las columnas, o <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> para las columnas pero no para las filas) y también está habilitado, el ajuste de tamaño también se produce siempre que cambia la otra dimensión. Por ejemplo, si las filas pero no las columnas están configuradas <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> para el ajuste automático de tamaño y está habilitada, los usuarios pueden arrastrar los divisores de columna para cambiar el ancho de una columna y los altos de las filas se ajustarán automáticamente para que el contenido de la celda se siga mostrando por completo.  
  
 Si configura filas y columnas para el ajuste automático de tamaño basado en contenido <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> y está habilitado <xref:System.Windows.Forms.DataGridView> , el control ajustará los tamaños cada vez que cambie el contenido de la celda y utilizará una relación de alto a ancho de celda ideal al calcular nuevos tamaños.  
  
 Para configurar el modo de ajuste de tamaño para encabezados y filas y para las columnas que no invalidan el valor del control, establezca una <xref:System.Windows.Forms.DataGridView> o varias de las propiedades siguientes:  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Para invalidar el modo de ajuste de tamaño de columna del control para una <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> columna individual, establezca su propiedad <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>en un valor distinto de. El modo de ajuste de tamaño de una columna está determinado <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> realmente por su propiedad. El valor de esta propiedad se basa en el valor de <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> la propiedad de la columna, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>a menos que ese valor sea, <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> en cuyo caso se hereda el valor del control.  
  
 Use el cambio de tamaño automático basado en el contenido con precaución al trabajar con grandes cantidades de datos. Para evitar las penalizaciones de rendimiento, use los modos de ajuste automático de tamaño que calculan los tamaños basados solo en las filas mostradas en lugar de analizar todas las filas del control. Para obtener el máximo rendimiento, utilice el cambio de tamaño mediante programación para que pueda cambiar el tamaño en momentos específicos, como inmediatamente después de cargar los nuevos datos.  
  
 Los modos de ajuste automático de tamaño basados en contenido no afectan a las filas, columnas o encabezados que haya ocultado estableciendo la propiedad <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> de fila o columna <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> , o el `false`control o <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> las propiedades en. Por ejemplo, si una columna está oculta una vez que se ajusta automáticamente para ajustarse a un valor de celda grande, la columna oculta no cambiará su tamaño si se elimina la fila que contiene el valor de celda grande. El ajuste automático de tamaño no se produce cuando cambia la visibilidad, <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> por lo que `true` el cambio de la propiedad de columna a no obliga a que vuelva a calcular su tamaño en función de su contenido actual.  
  
 El cambio de tamaño basado en contenido mediante programación afecta a filas, columnas y encabezados, independientemente de su visibilidad.  
  
## <a name="programmatic-resizing"></a>Cambio de tamaño mediante programación  
 Cuando el ajuste de tamaño automático está deshabilitado, puede establecer mediante programación el ancho o el alto exacto de filas, columnas o encabezados a través de las siguientes propiedades:  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 También puede cambiar mediante programación el tamaño de filas, columnas y encabezados para ajustar su contenido mediante los métodos siguientes:  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Estos métodos cambiarán el tamaño de las filas, columnas o encabezados una vez, en lugar de configurarlos para el cambio de tamaño continuo. Los nuevos tamaños se calculan automáticamente para mostrar todo el contenido de la celda sin recortes. Sin embargo, al cambiar mediante programación el tamaño <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> de las columnas <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>que tienen valores de propiedad de, se usan los anchos basados en el contenido calculados para <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> ajustar proporcionalmente los valores de las propiedades de columna y los anchos de columna reales. después, se calcula según estas nuevas proporciones para que todas las columnas rellenen el área de presentación disponible del control.  
  
 El cambio de tamaño mediante programación es útil para evitar las penalizaciones de rendimiento con el cambio de tamaño continuo. También resulta útil proporcionar tamaños iniciales para filas, columnas y encabezados de tamaño ajustable por el usuario, así como para el modo de relleno de columnas.  
  
 Normalmente, se llama a los métodos de cambio de tamaño mediante programación en momentos concretos. Por ejemplo, puede cambiar mediante programación el tamaño de todas las columnas inmediatamente después de cargar los datos, o puede cambiar mediante programación el tamaño de una fila concreta después de que se haya modificado un valor de celda determinado.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Personalizar el comportamiento de ajuste de tamaño basado en contenido  
 Puede personalizar los comportamientos de ajuste de tamaño al <xref:System.Windows.Forms.DataGridView> trabajar con tipos de celda, fila y columna derivados invalidando los <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> métodos, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>o o llamando a las sobrecargas del <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>método de cambio <xref:System.Windows.Forms.DataGridView> de tamaño protegido en una derivada control. Las sobrecargas del método de cambio de tamaño protegido están diseñadas para funcionar en pares con el fin de lograr una relación de alto y ancho de celda ideal, evitando celdas demasiado anchas o grandes. Por ejemplo, si se llama a `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` la sobrecarga <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> del método y se pasa un valor de `false` para el <xref:System.Boolean> parámetro, la sobrecarga calculará los altos y anchos ideales para las celdas de la fila, pero ajustará el alto de las filas. tan. A continuación, debe llamar <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> al método para ajustar el ancho de las columnas al ideal calculado.  
  
## <a name="content-based-sizing-options"></a>Opciones de ajuste de tamaño basado en contenido  
 Las enumeraciones usadas por las propiedades y los métodos de ajuste de tamaño tienen valores similares para el ajuste de tamaño basado en contenido. Con estos valores, puede limitar qué celdas se usan para calcular los tamaños preferidos. En todas las enumeraciones de tamaño, los valores cuyos nombres hacen referencia a las celdas mostradas limitan sus cálculos a las celdas de las filas mostradas. Excluir filas resulta útil para evitar una reducción del rendimiento cuando se trabaja con una gran cantidad de filas. También puede restringir los cálculos a los valores de celda en las celdas de encabezado o de no encabezado.  
  
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
- [Cómo: Establecer los modos de cambio de tamaño del control DataGridView Windows Forms](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
