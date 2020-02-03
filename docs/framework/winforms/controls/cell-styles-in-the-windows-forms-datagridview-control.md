---
title: Estilos de celda en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: fe56033a5adbe7719c64695c8f9ebc4f3644fc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746155"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Estilos de celda en el control DataGridView de formularios Windows Forms
Cada celda del control <xref:System.Windows.Forms.DataGridView> puede tener su propio estilo, como el formato de texto, el color de fondo, el color de primer plano y la fuente. No obstante, por lo general, varias celdas compartirán determinadas características de estilo.  
  
 Los grupos de celdas que comparten estilos pueden incluir todas las celdas de filas o columnas concretas, todas las celdas que contienen valores concretos o todas las celdas del control. Dado que estos grupos se superponen, cada celda puede obtener su información de estilo desde más de un lugar. Por ejemplo, puede que desee que todas las celdas de un control de <xref:System.Windows.Forms.DataGridView> usen la misma fuente, pero solo las celdas de las columnas de moneda para usar el formato de moneda y solo las celdas de moneda con números negativos para usar un color de primer plano rojo.  
  
## <a name="the-datagridviewcellstyle-class"></a>La clase DataGridViewCellStyle  
 La clase <xref:System.Windows.Forms.DataGridViewCellStyle> contiene las siguientes propiedades relacionadas con el estilo visual:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Esta clase también contiene las siguientes propiedades relacionadas con el formato:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Para obtener más información sobre estas propiedades y otras propiedades de estilo de celda, vea la documentación de referencia de <xref:System.Windows.Forms.DataGridViewCellStyle> y los temas que se enumeran en la sección Vea también más adelante.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Usar objetos DataGridViewCellStyle  
 Puede recuperar objetos <xref:System.Windows.Forms.DataGridViewCellStyle> de diversas propiedades de las clases <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>y <xref:System.Windows.Forms.DataGridViewCell> y sus clases derivadas. Si todavía no se ha establecido una de estas propiedades, al recuperar su valor se creará un nuevo objeto <xref:System.Windows.Forms.DataGridViewCellStyle>. También puede crear instancias de sus propios objetos <xref:System.Windows.Forms.DataGridViewCellStyle> y asignarlos a estas propiedades.  
  
 Puede evitar la duplicación innecesaria de información de estilo compartiendo objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varios elementos <xref:System.Windows.Forms.DataGridView>. Dado que los estilos establecidos en los niveles de control, columna y fila se filtran por cada nivel hasta el nivel de celda, también puede evitar la duplicación de estilo estableciendo únicamente las propiedades de estilo en cada nivel que difieren de los niveles anteriores. Esto se describe con más detalle en la sección herencia de estilo que se muestra a continuación.  
  
 En la tabla siguiente se enumeran las propiedades principales que obtienen o establecen objetos <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
|Propiedad|Clases|Descripción|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>y clases derivadas|Obtiene o establece los estilos predeterminados utilizados por todas las celdas de todo el control (incluidas las celdas de encabezado), en una columna o en una fila.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados utilizados por todas las filas del control. Esto no incluye las celdas de encabezado.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados usados por filas alternas en el control. Se usa para crear un efecto como libro de contabilidad.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados usados por los encabezados de fila del control. Reemplazado por el tema actual si los estilos visuales están habilitados.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados usados por los encabezados de columna del control. Reemplazado por el tema actual si los estilos visuales están habilitados.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> y clases derivadas|Obtiene o establece los estilos especificados en el nivel de celda. Estos estilos invalidan los heredados de los niveles superiores.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>y clases derivadas|Obtiene todos los estilos aplicados actualmente a la celda, fila o columna, incluidos los estilos heredados de niveles superiores.|  
  
 Como se mencionó anteriormente, al obtener el valor de una propiedad de estilo se crea automáticamente una instancia de un nuevo objeto <xref:System.Windows.Forms.DataGridViewCellStyle> si la propiedad no se ha establecido previamente. Para evitar la creación de estos objetos innecesariamente, las clases de fila y de columna tienen una propiedad <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> que puede comprobar para determinar si se ha establecido la propiedad <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A>. Del mismo modo, las clases de celda tienen una propiedad <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> que indica si se ha establecido la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A>.  
  
 Cada una de las propiedades de estilo tiene un evento *PropertyName*`Changed` correspondiente en el control <xref:System.Windows.Forms.DataGridView>. En el caso de las propiedades de fila, columna y celda, el nombre del evento comienza por "`Row`", "`Column`" o "`Cell`" (por ejemplo, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Cada uno de estos eventos se produce cuando la propiedad de estilo correspondiente se establece en un objeto de <xref:System.Windows.Forms.DataGridViewCellStyle> diferente. Estos eventos no se producen cuando se recupera un objeto de <xref:System.Windows.Forms.DataGridViewCellStyle> de una propiedad de estilo y se modifican sus valores de propiedad. Para responder a los cambios en los propios objetos de estilo de celda, controle el evento <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>.  
  
## <a name="style-inheritance"></a>Herencia de estilo  
 Cada <xref:System.Windows.Forms.DataGridViewCell> obtiene su apariencia de su <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad. El objeto <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por esta propiedad hereda sus valores de una jerarquía de propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle>. Estas propiedades se enumeran a continuación en el orden en que el <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> para las celdas que no son de encabezado obtiene sus valores.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (solo para las celdas de filas con números de índice impares)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 En el caso de las celdas de encabezado de fila y de columna, la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> se rellena con los valores de la siguiente lista de propiedades de origen en el orden especificado.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 En el diagrama siguiente se muestra este proceso.  
  
 ![Propiedades de tipo DataGridViewCellStyle](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "Diagrama de herencia de DataGridViewCells")  
  
 También puede tener acceso a los estilos heredados por filas y columnas específicas. La propiedad <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> columna hereda sus valores de las siguientes propiedades.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 La propiedad Row <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> hereda sus valores de las siguientes propiedades.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (solo para las celdas de filas con números de índice impares)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Para cada propiedad de un objeto <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por una propiedad `InheritedStyle`, el valor de la propiedad se obtiene del primer estilo de celda de la lista adecuada que tiene la propiedad correspondiente establecida en un valor distinto de los valores predeterminados de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 En la tabla siguiente se muestra cómo se hereda el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> de una celda de ejemplo de la columna que lo contiene.  
  
|Propiedad de tipo `DataGridViewCellStyle`|Ejemplo de `ForeColor` valor para el objeto recuperado|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 En este caso, el valor de <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> de la fila de la celda es el primer valor real de la lista. Esto se convierte en el valor de propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> de la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>de la celda.  
  
 En el diagrama siguiente se muestra cómo diferentes propiedades de <xref:System.Windows.Forms.DataGridViewCellStyle> pueden heredar sus valores de diferentes lugares.  
  
 ![Herencia de&#45;valores de propiedad de DataGridView](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells diagrama de herencia de valores")  
  
 Al aprovechar la herencia de estilo, puede proporcionar los estilos adecuados para todo el control sin tener que especificar la misma información en varios lugares.  
  
 Aunque las celdas de encabezado participan en la herencia de estilo como se describe, los objetos devueltos por las propiedades <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> del control <xref:System.Windows.Forms.DataGridView> tienen valores de propiedad iniciales que invalidan los valores de propiedad del objeto devuelto por la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. Si desea que las propiedades establecidas para el objeto devuelto por la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> se apliquen a los encabezados de fila y de columna, debe establecer las propiedades correspondientes de los objetos devueltos por las propiedades <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> en los valores predeterminados indicados para la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
> [!NOTE]
> Si los estilos visuales están habilitados, los encabezados de fila y de columna (excepto el <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) se aplican automáticamente de estilo al tema actual, invalidando los estilos especificados por estas propiedades.  
  
 Los tipos <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>y <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> también inicializan algunos valores del objeto devuelto por la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> de columna. Para obtener más información, consulte la documentación de referencia de estos tipos.  
  
## <a name="setting-styles-dynamically"></a>Establecer estilos dinámicamente  
 Para personalizar los estilos de las celdas con valores concretos, implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. Los controladores de este evento reciben un argumento del tipo de <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>. Este objeto contiene propiedades que permiten determinar el valor de la celda que se está formateando junto con su ubicación en el control <xref:System.Windows.Forms.DataGridView>. Este objeto también contiene una propiedad <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> que se inicializa con el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> de la celda a la que se va a dar formato. Puede modificar las propiedades de estilo de celda para especificar la información de estilo adecuada para el valor de celda y la ubicación.  
  
> [!NOTE]
> Los eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> también reciben un objeto <xref:System.Windows.Forms.DataGridViewCellStyle> en los datos de evento, pero en su caso, se trata de una copia de la propiedad <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> de filas con fines de solo lectura y los cambios en ella no afectan al control.  
  
 También puede modificar dinámicamente los estilos de celdas individuales en respuesta a eventos como los eventos <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> y <xref:System.Windows.Forms.DataGridView.CellMouseLeave>. Por ejemplo, en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellMouseEnter>, podría almacenar el valor actual del color de fondo de la celda (recuperado a través de la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A> de la celda) y, a continuación, establecerlo en un nuevo color que resalte la celda cuando se mantenga el mouse sobre ella. En un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellMouseLeave>, puede restaurar el color de fondo al valor original.  
  
> [!NOTE]
> Almacenar en caché los valores almacenados en la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A> de la celda es importante independientemente de si se ha establecido un valor de estilo determinado. Si reemplaza temporalmente una configuración de estilo, restaurarla a su estado original "sin establecer" garantiza que la celda volverá a heredar la configuración de estilo de un nivel superior. Si necesita determinar el estilo real en vigor para una celda, independientemente de si el estilo es heredado, utilice la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> de la celda.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Formato de datos en el control DataGridView de Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
