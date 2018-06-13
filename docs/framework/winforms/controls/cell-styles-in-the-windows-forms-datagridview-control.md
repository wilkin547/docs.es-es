---
title: Estilos de celda en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: 463fbbffe1e88991934f08fbe7e7445b2e233081
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529664"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Estilos de celda en el control DataGridView de formularios Windows Forms
Cada celda de la <xref:System.Windows.Forms.DataGridView> control puede tener su propio estilo, como formato de texto, color de fondo, color de primer plano y fuente. Por lo general, sin embargo, varias celdas comparten características de estilo determinado.  
  
 Grupos de celdas que comparten estilos pueden incluir todas las celdas dentro de determinadas filas o columnas, todas las celdas que contengan valores específicos o todas las celdas del control. Dado que estos grupos se superponen, cada celda puede obtener su información de estilo de más de un lugar. Por ejemplo, puede querer todas las celdas en una <xref:System.Windows.Forms.DataGridView> control para utilizar la misma fuente, pero solo las celdas de las columnas de moneda para usar el formato de moneda y solo las celdas de moneda con los números negativos para usar un color de primer plano rojo.  
  
## <a name="the-datagridviewcellstyle-class"></a>La clase DataGridViewCellStyle  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> clase contiene las siguientes propiedades relacionadas con el estilo visual:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Esta clase también contiene las siguientes propiedades relacionadas con el formato:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Para obtener más información sobre estas propiedades y otras propiedades de estilo de celda, vea el <xref:System.Windows.Forms.DataGridViewCellStyle> documentación de referencia y los temas enumeran en la sección Vea también.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Utilizar objetos DataGridViewCellStyle  
 Puede recuperar <xref:System.Windows.Forms.DataGridViewCellStyle> objetos desde distintas propiedades de la <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, y <xref:System.Windows.Forms.DataGridViewCell> las clases y sus clases derivadas. Si una de estas propiedades no se ha establecido, se creará un nuevo recuperar su valor <xref:System.Windows.Forms.DataGridViewCellStyle> objeto. También puede crear sus propios <xref:System.Windows.Forms.DataGridViewCellStyle> objetos y asignarlos a estas propiedades.  
  
 Puede evitar la duplicación innecesaria de información de estilo compartiendo <xref:System.Windows.Forms.DataGridViewCellStyle> objetos entre varios <xref:System.Windows.Forms.DataGridView> elementos. Dado que los estilos establecidos en el control, columna y filtro de niveles de fila hacia abajo a través de cada nivel para el nivel de celda, se puede evitar la duplicación de estilo estableciendo únicamente las propiedades de estilo en cada nivel que difieren de los niveles anteriores. Esto se describe con más detalle en la siguiente sección de herencia de estilos.  
  
 En la tabla siguiente se enumera las propiedades principales que obtienen o establecen <xref:System.Windows.Forms.DataGridViewCellStyle> objetos.  
  
|Property|Clases|Descripción|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>y sus clases derivadas|Obtiene o establece los estilos predeterminados utilizados por todas las celdas en el control completo (incluidas las celdas de encabezado), en una columna o en una fila.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados utilizados por todas las filas en el control. Esto no incluye las celdas de encabezado.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados utilizados por las filas alternas en el control. Se utiliza para crear un efecto de carta.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados utilizados por los encabezados de fila del control. Se reemplaza por el tema actual si se habilitan estilos visuales.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece los estilos de celda predeterminados utilizados por los encabezados de columna del control. Se reemplaza por el tema actual si se habilitan estilos visuales.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> y las clases derivadas|Obtiene o establece los estilos especificados en el nivel de celda. Estos estilos reemplazan a los heredados de los niveles superiores.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>y sus clases derivadas|Obtiene todos los estilos que se aplique actualmente a la celda, fila o columna, incluso estilos heredados de los niveles superiores.|  
  
 Como se mencionó anteriormente, obteniendo el valor de una propiedad de estilo automáticamente crea un nuevo <xref:System.Windows.Forms.DataGridViewCellStyle> si no se ha establecido anteriormente la propiedad del objeto. Para evitar crear estos objetos innecesariamente, las clases de fila y columna tienen un <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> propiedad que puede comprobar para determinar si el <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> se ha establecido la propiedad. De forma similar, las clases de celda tienen un <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> propiedad que indica si el <xref:System.Windows.Forms.DataGridViewCell.Style%2A> se ha establecido la propiedad.  
  
 Cada una de las propiedades de estilo tiene su correspondiente *PropertyName* `Changed` evento en el <xref:System.Windows.Forms.DataGridView> control. Para propiedades de celda, columna y fila, el nombre del evento comienza con "`Row`","`Column`", o "`Cell`" (por ejemplo, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Cada uno de estos eventos se produce cuando la propiedad de estilo correspondiente se establece en otro <xref:System.Windows.Forms.DataGridViewCellStyle> objeto. Estos eventos no se producen cuando se recupera un <xref:System.Windows.Forms.DataGridViewCellStyle> de objetos de una propiedad de estilo y modificar sus valores de propiedad. Para responder a los cambios en los propios objetos de estilo de celda, controle el <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> eventos.  
  
## <a name="style-inheritance"></a>Herencia de estilos  
 Cada <xref:System.Windows.Forms.DataGridViewCell> obtiene su apariencia de su <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad. El <xref:System.Windows.Forms.DataGridViewCellStyle> objeto devuelto por esta propiedad hereda sus valores de una jerarquía de propiedades del tipo <xref:System.Windows.Forms.DataGridViewCellStyle>. Estas propiedades se enumeran a continuación en el orden en que el <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> para las celdas de encabezado no obtiene sus valores.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (solo para las celdas en filas con números de índice impares)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Para las celdas de encabezado de fila y columna, el <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad se rellena con los valores de la siguiente lista de propiedades de origen en el orden especificado.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 El siguiente diagrama ilustra este proceso.  
  
 ![Propiedades del tipo DataGridViewCellStyle](../../../../docs/framework/winforms/controls/media/datagridviewcells1.gif "DataGridViewCells1")  
  
 También puede tener acceso a los estilos heredados por filas y columnas concretas. La columna <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> propiedad hereda sus valores de las siguientes propiedades.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 La fila <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> propiedad hereda sus valores de las siguientes propiedades.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (solo para las celdas en filas con números de índice impares)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Para cada propiedad en un <xref:System.Windows.Forms.DataGridViewCellStyle> objeto devuelto por una `InheritedStyle` propiedad, se obtiene el valor de propiedad desde el primer estilo de celda en la lista correspondiente que tiene la propiedad correspondiente establecida en un valor distinto de la <xref:System.Windows.Forms.DataGridViewCellStyle> los valores predeterminados de la clase.  
  
 La tabla siguiente se muestra cómo el <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> valor de propiedad para una celda del ejemplo se hereda de la columna que lo contiene.  
  
|propiedad de tipo `DataGridViewCellStyle`|En el ejemplo se `ForeColor` valor para el objeto recuperado|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 En este caso, el <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> valor de fila de la celda es el primer valor real en la lista. Esto se convierte en el <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> valor de la propiedad de la celda <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 El siguiente diagrama muestra cómo diferentes <xref:System.Windows.Forms.DataGridViewCellStyle> propiedades pueden heredar sus valores de distintos lugares.  
  
 ![Propiedad DataGridView&#45;herencia del valor de](../../../../docs/framework/winforms/controls/media/datagridviewcells2.gif "DataGridViewCells2")  
  
 Aprovechando las ventajas de la herencia de estilos, puede proporcionar estilos apropiados para todo el control sin tener que especificar la misma información en varios lugares.  
  
 Aunque las celdas de encabezado participan en la herencia de estilos tal como se describe, los objetos devuelven por la <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> propiedades de la <xref:System.Windows.Forms.DataGridView> control tienen valores de propiedad iniciales que reemplazan los valores de propiedad del objeto devuelto por el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad. Si desea que las propiedades establecidas para el objeto devuelto por la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad que se va a aplicar a los encabezados de fila y columna, debe establecer las propiedades correspondientes de los objetos devueltos por la <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> indican propiedades a los valores predeterminados para el <xref:System.Windows.Forms.DataGridViewCellStyle> clase.  
  
> [!NOTE]
>  Si se habilitan estilos visuales, los encabezados de fila y columna (excepto la <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) reciben automáticamente el estilo del tema actual, reemplazando cualquier estilo especificado por estas propiedades.  
  
 El <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, y <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> tipos también inicializan algunos valores del objeto devuelto por la columna <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad. Para obtener más información, consulte la documentación de referencia para estos tipos.  
  
## <a name="setting-styles-dynamically"></a>Establecer los estilos dinámicamente  
 Para personalizar los estilos de celdas con valores concretos, implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> eventos. Controladores para este evento reciben un argumento de la <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> tipo. Este objeto contiene propiedades que permiten determinar el valor de la celda que se está dando formato junto con su ubicación en la <xref:System.Windows.Forms.DataGridView> control. Este objeto también contiene un <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> propiedad que se inicializa en el valor de la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad de la celda que se está dando formatea. Puede modificar las propiedades de estilo de celda para especificar la información de estilo adecuada a la ubicación y el valor de la celda.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> eventos también reciben un <xref:System.Windows.Forms.DataGridViewCellStyle> datos del objeto en el evento, pero en su caso, es una copia de la fila <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> propiedad para fines de solo lectura y los cambios en él no afecta al control.  
  
 Dinámicamente también puede modificar los estilos de celdas individuales en respuesta a eventos como la <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> y <xref:System.Windows.Forms.DataGridView.CellMouseLeave> eventos. Por ejemplo, en un controlador para el <xref:System.Windows.Forms.DataGridView.CellMouseEnter> eventos, podría almacenar el valor actual del color de fondo de celda (recuperados a través de la celda <xref:System.Windows.Forms.DataGridViewCell.Style%2A> propiedad), a continuación, se establece en un nuevo color que resalte la celda cuando el mouse se desplaza sobre él. En un controlador para el <xref:System.Windows.Forms.DataGridView.CellMouseLeave> evento, a continuación, puede restaurar el color de fondo al valor original.  
  
> [!NOTE]
>  Almacenamiento en caché los valores almacenados en la celda <xref:System.Windows.Forms.DataGridViewCell.Style%2A> propiedad es importante independientemente de si se establece un valor de estilo determinado. Si reemplaza temporalmente una configuración de estilo, restaurar a su estado original "no configurada" garantiza que la celda volverá a heredar la configuración de estilo de un nivel más alto. Si necesita determinar el estilo real en vigor para una celda, independientemente de si se hereda el estilo, utilice la celda <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> propiedad.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Formato de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
