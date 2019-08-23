---
title: Estilos de celda en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: be4c47db5c56685a84153a9ae4a9a2fe14c6adad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917768"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Estilos de celda en el control DataGridView de formularios Windows Forms
Cada celda del <xref:System.Windows.Forms.DataGridView> control puede tener su propio estilo, como el formato de texto, el color de fondo, el color de primer plano y la fuente. No obstante, por lo general, varias celdas compartirán determinadas características de estilo.  
  
 Los grupos de celdas que comparten estilos pueden incluir todas las celdas de filas o columnas concretas, todas las celdas que contienen valores concretos o todas las celdas del control. Dado que estos grupos se superponen, cada celda puede obtener su información de estilo desde más de un lugar. Por ejemplo, puede que desee que todas las celdas <xref:System.Windows.Forms.DataGridView> de un control usen la misma fuente, pero solo las celdas de las columnas de moneda usen el formato de moneda y solo las celdas de moneda con números negativos para usar un color de primer plano rojo.  
  
## <a name="the-datagridviewcellstyle-class"></a>La clase DataGridViewCellStyle  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> clase contiene las siguientes propiedades relacionadas con el estilo visual:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Esta clase también contiene las siguientes propiedades relacionadas con el formato:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Para obtener más información sobre estas propiedades y otras propiedades de estilo de celda, <xref:System.Windows.Forms.DataGridViewCellStyle> vea la documentación de referencia y los temas enumerados en la sección Vea también más adelante.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Usar objetos DataGridViewCellStyle  
 Puede <xref:System.Windows.Forms.DataGridViewCellStyle> recuperar objetos de varias propiedades de las <xref:System.Windows.Forms.DataGridView>clases, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>y <xref:System.Windows.Forms.DataGridViewCell> y sus clases derivadas. Si todavía no se ha establecido una de estas propiedades, al recuperar su valor se creará un <xref:System.Windows.Forms.DataGridViewCellStyle> nuevo objeto. También puede crear instancias de sus propios <xref:System.Windows.Forms.DataGridViewCellStyle> objetos y asignarlos a estas propiedades.  
  
 Puede evitar la duplicación innecesaria de información de <xref:System.Windows.Forms.DataGridViewCellStyle> estilo compartiendo objetos <xref:System.Windows.Forms.DataGridView> entre varios elementos. Dado que los estilos establecidos en los niveles de control, columna y fila se filtran por cada nivel hasta el nivel de celda, también puede evitar la duplicación de estilo estableciendo únicamente las propiedades de estilo en cada nivel que difieren de los niveles anteriores. Esto se describe con más detalle en la sección herencia de estilo que se muestra a continuación.  
  
 En la tabla siguiente se enumeran las propiedades principales que <xref:System.Windows.Forms.DataGridViewCellStyle> obtienen o establecen objetos.  
  
|Propiedad|Clases|DESCRIPCIÓN|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>,yclasesderivadas <xref:System.Windows.Forms.DataGridViewRow>|Obtiene o establece los estilos predeterminados utilizados por todas las celdas de todo el control (incluidas las celdas de encabezado), en una columna o en una fila.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados utilizados por todas las filas del control. Esto no incluye las celdas de encabezado.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados usados por filas alternas en el control. Se usa para crear un efecto como libro de contabilidad.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados usados por los encabezados de fila del control. Reemplazado por el tema actual si los estilos visuales están habilitados.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados usados por los encabezados de columna del control. Reemplazado por el tema actual si los estilos visuales están habilitados.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell>y clases derivadas|Obtiene o establece los estilos especificados en el nivel de celda. Estos estilos invalidan los heredados de los niveles superiores.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>,yclasesderivadas <xref:System.Windows.Forms.DataGridViewColumn>|Obtiene todos los estilos aplicados actualmente a la celda, fila o columna, incluidos los estilos heredados de niveles superiores.|  
  
 Como se mencionó anteriormente, al obtener el valor de una propiedad de estilo se crea <xref:System.Windows.Forms.DataGridViewCellStyle> automáticamente una instancia de un nuevo objeto si la propiedad no se ha establecido previamente. Para evitar la creación de estos objetos innecesariamente, las clases de fila <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> y de columna tienen una propiedad que se puede <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> comprobar para determinar si se ha establecido la propiedad. Del mismo modo, las clases de <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> celda tienen una propiedad que <xref:System.Windows.Forms.DataGridViewCell.Style%2A> indica si se ha establecido la propiedad.  
  
 Cada una de las propiedades de estilo tiene un evento *PropertyName* `Changed` correspondiente <xref:System.Windows.Forms.DataGridView> en el control. En el caso de las propiedades de fila, columna y celda, el nombre del evento`Row`comienza por "`Column`", ""`Cell`o "" (por <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>ejemplo,). Cada uno de estos eventos se produce cuando la propiedad de estilo correspondiente se establece <xref:System.Windows.Forms.DataGridViewCellStyle> en un objeto diferente. Estos eventos no se producen cuando se recupera un <xref:System.Windows.Forms.DataGridViewCellStyle> objeto de una propiedad de estilo y se modifican sus valores de propiedad. Para responder a los cambios en los propios objetos de estilo de celda <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> , controle el evento.  
  
## <a name="style-inheritance"></a>Herencia de estilo  
 Cada <xref:System.Windows.Forms.DataGridViewCell> obtiene su apariencia de su <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad. El <xref:System.Windows.Forms.DataGridViewCellStyle> objeto devuelto por esta propiedad hereda sus valores de una jerarquía de propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle>. Estas propiedades se enumeran a continuación en el orden en <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> que el para las celdas que no son de encabezado obtiene sus valores.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(solo para las celdas de filas con números de índice impares)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 En el caso de las celdas de encabezado <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> de fila y de columna, la propiedad se rellena con los valores de la siguiente lista de propiedades de origen en el orden especificado.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 En el siguiente diagrama se ilustra este proceso.  
  
 ![Propiedades de tipo DataGridViewCellStyle](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "Diagrama de herencia de DataGridViewCells")  
  
 También puede tener acceso a los estilos heredados por filas y columnas específicas. La propiedad <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> de columna hereda sus valores de las siguientes propiedades.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 La propiedad <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> Row hereda sus valores de las propiedades siguientes.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(solo para las celdas de filas con números de índice impares)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Para cada propiedad de un <xref:System.Windows.Forms.DataGridViewCellStyle> objeto devuelto por `InheritedStyle` una propiedad, el valor de la propiedad se obtiene del primer estilo de celda de la lista correspondiente que tiene la propiedad correspondiente establecida en un valor <xref:System.Windows.Forms.DataGridViewCellStyle> distinto de los valores predeterminados de la clase.  
  
 En la tabla siguiente se muestra cómo <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> se hereda el valor de propiedad de una celda de ejemplo de la columna que lo contiene.  
  
|Propiedad de tipo`DataGridViewCellStyle`|Valor `ForeColor` de ejemplo para el objeto recuperado|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 En este caso, el <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> valor de la fila de la celda es el primer valor real de la lista. Esto se convierte <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> en el valor de propiedad de <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>la propiedad de la celda.  
  
 En el diagrama siguiente se muestra cómo <xref:System.Windows.Forms.DataGridViewCellStyle> diferentes propiedades pueden heredar sus valores de diferentes lugares.  
  
 ![Herencia de&#45;valores de propiedad de DataGridView](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells diagrama de herencia de valores")  
  
 Al aprovechar la herencia de estilo, puede proporcionar los estilos adecuados para todo el control sin tener que especificar la misma información en varios lugares.  
  
 Aunque las celdas de encabezado participan en la herencia de estilo como se describe, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> los <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> objetos devueltos por las propiedades y del <xref:System.Windows.Forms.DataGridView> control tienen valores de propiedad iniciales que invalidan los valores de propiedad del objeto devuelto por <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad. Si desea que las propiedades establecidas para el objeto devuelto por <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> la propiedad se apliquen a los encabezados de fila y de columna, debe establecer las propiedades correspondientes de los objetos <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> devueltos por las propiedades y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> en los valores predeterminados indicados. para la <xref:System.Windows.Forms.DataGridViewCellStyle> clase.  
  
> [!NOTE]
> Si los estilos visuales están habilitados, los encabezados de fila y de columna ( <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>excepto para) se aplican automáticamente de estilo al tema actual, invalidando los estilos especificados por estas propiedades.  
  
 Los <xref:System.Windows.Forms.DataGridViewButtonColumn>tipos <xref:System.Windows.Forms.DataGridViewImageColumn>, <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> también inicializan algunos valores del objeto devuelto por la propiedad de columna. Para obtener más información, consulte la documentación de referencia de estos tipos.  
  
## <a name="setting-styles-dynamically"></a>Establecer estilos dinámicamente  
 Para personalizar los estilos de las celdas con valores concretos, implemente un controlador <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> para el evento. Los <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> controladores de este evento reciben un argumento del tipo. Este objeto contiene propiedades que permiten determinar el valor de la celda que se está formateando junto con su ubicación <xref:System.Windows.Forms.DataGridView> en el control. Este objeto también contiene una <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> propiedad que se inicializa en el valor de la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad de la celda a la que se va a dar formato. Puede modificar las propiedades de estilo de celda para especificar la información de estilo adecuada para el valor de celda y la ubicación.  
  
> [!NOTE]
> Los <xref:System.Windows.Forms.DataGridView.RowPrePaint> eventos <xref:System.Windows.Forms.DataGridView.RowPostPaint> y también reciben un <xref:System.Windows.Forms.DataGridViewCellStyle> objeto en los datos de evento, pero en su caso, es una copia de la propiedad <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> Row para fines de solo lectura y los cambios en ella no afectan al control.  
  
 También puede modificar dinámicamente los estilos de celdas individuales en respuesta a eventos como los <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> eventos y. <xref:System.Windows.Forms.DataGridView.CellMouseLeave> Por ejemplo, en un controlador para el <xref:System.Windows.Forms.DataGridView.CellMouseEnter> evento, puede almacenar el valor actual del color de fondo de la celda (recuperado a través <xref:System.Windows.Forms.DataGridViewCell.Style%2A> de la propiedad de la celda) y, a continuación, establecerlo en un nuevo color que resaltará la celda cuando se mantenga el mouse sobre ella. En un controlador para el <xref:System.Windows.Forms.DataGridView.CellMouseLeave> evento, puede restaurar el color de fondo al valor original.  
  
> [!NOTE]
> Almacenar en caché los valores almacenados en la <xref:System.Windows.Forms.DataGridViewCell.Style%2A> propiedad de la celda es importante independientemente de si se ha establecido un valor de estilo determinado. Si reemplaza temporalmente una configuración de estilo, restaurarla a su estado original "sin establecer" garantiza que la celda volverá a heredar la configuración de estilo de un nivel superior. Si necesita determinar el estilo real en vigor para una celda, independientemente de si el estilo es heredado, utilice la propiedad de <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> la celda.  
  
## <a name="see-also"></a>Vea también

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
- [Cómo: Establecer estilos de celda predeterminados para el control DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Formato de datos en el control DataGridView de Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
