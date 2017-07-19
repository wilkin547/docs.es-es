---
title: "Estilos de celda en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, estilos"
  - "cuadrículas de datos, estilos de celda"
  - "DataGridView (control) [Windows Forms], estilos de celda"
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Estilos de celda en el control DataGridView de formularios Windows Forms
Cada celda dentro del control <xref:System.Windows.Forms.DataGridView> puede tener su propio estilo, como formato de texto, color de fondo, color de primer plano y fuente.  Pero normalmente, varias celdas comparten características de estilo determinadas.  
  
 Los grupos de celdas que comparten estilo podrían ser todas las celdas de unas filas y columnas determinadas, todas las que contengan valores específicos o todas las de un control.  Puesto que estos grupos se superponen, cada celda puede obtener su información de estilo de varios sitios.  Por ejemplo, puede que desee que todas las celdas de un control <xref:System.Windows.Forms.DataGridView> utilicen la misma fuente, pero que sólo las celdas de las columnas de divisa utilicen formato de divisa y que de esas celdas sólo las que contengan números negativos utilicen un color rojo de primer plano.  
  
## Las clase DataGridViewCellStyle  
 La clase <xref:System.Windows.Forms.DataGridViewCellStyle> contiene las propiedades siguientes relacionadas con el estilo visual:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Esta clase también contiene las propiedades siguientes relacionadas con el formato:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Para obtener más información acerca de estas propiedades y de otras propiedades de estilo de celda, consulte la documentación de referencia de <xref:System.Windows.Forms.DataGridViewCellStyle> y los temas enumerados en la sección Vea también que se encuentra más abajo.  
  
## Utilizar objetos DataGridViewCellStyle  
 Puede recuperar los objetos <xref:System.Windows.Forms.DataGridViewCellStyle> de las distintas propiedades de <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> y las clases <xref:System.Windows.Forms.DataGridViewCell> y sus clases derivadas.  Si todavía no se ha establecido una de estas propiedades, al recuperar su valor, se creará un nuevo objeto <xref:System.Windows.Forms.DataGridViewCellStyle>.  También puede crear instancias de sus propios objetos <xref:System.Windows.Forms.DataGridViewCellStyle> y asignarlos a estas propiedades.  
  
 Puede evitar la duplicación innecesaria de información de estilo compartiendo los objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varios elementos <xref:System.Windows.Forms.DataGridView>.  Puesto que los estilos establecidos en el control, la columna y los niveles de fila se aplican en cada nivel hasta el nivel de celda, también puede evitar la duplicación del estilo estableciendo sólo estas propiedades de estilo en los niveles con estilo distinto al de los niveles anteriores.  Esto se describe con más detalle en la sección Herencia de estilos que se encuentra a continuación.  
  
 La tabla siguiente muestra las propiedades principales que obtienen o establecen objetos <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
|Propiedad.|Clases|Descripción|  
|----------------|------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> y las clases derivadas|Obtiene o establece estilos predeterminados utilizados por todas las celdas en el control completo \(incluso las celdas de encabezado\), en una columna o una fila.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece estilos de celda predeterminados utilizados por todas las filas del control.  Esto no incluye las celdas de encabezado.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece estilos de celda predeterminados utilizados por filas alternas del control.  Utilizado para crear un efecto de doble carta.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece estilos de celda predeterminados utilizados por los encabezados de fila de control.  Reemplazado por el tema actual si se habilitan estilos visuales.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Obtiene o establece estilos de celda predeterminados utilizados por los encabezados de columna de control.  Reemplazado por el tema actual si se habilitan estilos visuales.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> y clases derivadas|Obtiene o establece estilos especificados en el nivel celular.  Estos estilos reemplazan a los heredados de los niveles más altos.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn> y las clases derivadas|Obtiene todos los estilos actualmente aplicados a la celda, fila o columna, incluso estilos heredados de los niveles más altos.|  
  
 Tal como se explica anteriormente, obteniendo el valor de una propiedad de estilo automáticamente se crean instancias de un nuevo objeto <xref:System.Windows.Forms.DataGridViewCellStyle> si previamente no se ha establecido la propiedad.  Para evitar crear estos objetos de forma innecesaria, las clases de columnas y filas tienen una propiedad <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> que puede comprobar para determinar si se ha establecido la propiedad <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A>.  De forma similar, las clases de celdas tienen una propiedad <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> que indica si se ha establecido la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A>.  
  
 Cada una de las propiedades de estilo tiene un evento *nombreDePropiedad*`Changed` correspondiente en el control <xref:System.Windows.Forms.DataGridView>.  Para la fila, columna y propiedades de la celda, el nombre del evento comienza con "`Row`", "`Column`" o "`Cell`" \(por ejemplo, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>\).  Cada uno de estos eventos se produce cuando la propiedad de estilo correspondiente se establece en un objeto <xref:System.Windows.Forms.DataGridViewCellStyle> diferente.  Estos eventos no se provocan al recuperar un objeto <xref:System.Windows.Forms.DataGridViewCellStyle> de una propiedad de estilo y modifica sus valores de propiedad.  Para responder a los cambios de los objetos de estilo de celda, controle el evento <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>.  
  
## Herencia de estilos  
 Cada <xref:System.Windows.Forms.DataGridViewCell> obtiene su aspecto por medio de su propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  El objeto <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por esta propiedad hereda sus valores de una jerarquía de propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle>.  Estas propiedades se muestran a continuación en el orden en que <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> obtiene sus valores para las celdas que no son del encabezado.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName> \(sólo para las celdas en filas con números de índice impares\)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Para la fila y celdas del encabezado de columna, la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> se rellena con valores de la siguiente lista de propiedades de origen en el orden especificado.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 En el diagrama siguiente se muestra este proceso.  
  
 ![Propiedades del tipo DataGridViewCellStyle](../../../../docs/framework/winforms/controls/media/datagridviewcells1.png "DataGridViewCells1")  
  
 También puede tener acceso a los estilos heredados por filas y columnas concretas.  La columna la propiedad <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> hereda sus valores de las propiedades siguientes.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 La fila de la propiedad <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> hereda sus valores de las propiedades siguientes.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName> \(sólo para las celdas en filas con números de índice impares\)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Para cada propiedad del objeto <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por la propiedad `InheritedStyle` se obtiene el valor de propiedad del primer estilo de celda de la lista que contiene la propiedad correspondiente establecida en un valor distinto de los valores predeterminados de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 La tabla siguiente muestra cómo se hereda de la columna que lo contiene el valor de propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> para una celda del ejemplo.  
  
|Propiedad de tipo `DataGridViewCellStyle`|Ejemplo del valor `ForeColor` para el objeto recuperado|  
|-----------------------------------------------|-------------------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Red%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Black%2A?displayProperty=fullName>|  
  
 En este caso, el valor <xref:System.Drawing.Color.Red%2A?displayProperty=fullName> de la fila de la celda es el primer valor real en la lista.  Este se convierte en el valor de propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> de la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> de la celda.  
  
 El diagrama siguiente muestra cómo las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle> diferentes pueden heredar sus valores de distintos lugares.  
  
 ![Herencia de valores de la propiedad DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewcells2.png "DataGridViewCells2")  
  
 Aprovechando la herencia de estilos, puede proporcionar estilos adecuados para el control entero sin necesidad de especificar la misma información en distintos lugares.  
  
 Aunque las celdas del encabezado participan en la herencia de estilos tal como se ha descrito, los objetos devueltos por las propiedades <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> del control <xref:System.Windows.Forms.DataGridView> tienen valores de propiedad iniciales que reemplazan los valores de propiedad del objeto devuelto por la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>.  Si desea establecer las propiedades para el objeto devuelto por la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> para aplicarlo a los encabezados de columna y de fila, deberá establecer las propiedades correspondientes de los objetos devueltos por las propiedades <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> en los valores predeterminados indicados para la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
> [!NOTE]
>  Si están habilitados los estilos visuales, se aplica el estilo automáticamente a los encabezados de columna y de fila del tema activo \(excepto para <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>\) reemplazando cualquier estilo especificado por estas propiedades.  
  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn> y los tipos <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> también inicializan algunos valores del objeto devueltos por la columna la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>.  Para obtener más información, consulte la documentación de referencia para estos tipos.  
  
## Establecer los estilos dinámicamente  
 Para personalizar los estilos de celdas con valores determinados, implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>.  Los controladores para este evento reciben un argumento del tipo <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>.  Este objeto contiene propiedades que permiten determinar el valor de la célula a la que se aplica el formato junto con su ubicación en el control <xref:System.Windows.Forms.DataGridView>.  Este objeto también contiene una propiedad <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> inicializada en el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> de la celda a la que se está aplicando el formato.  Puede modificar las propiedades de estilo de celda para especificar la información de estilo adecuada para la ubicación y el valor de celda.  
  
> [!NOTE]
>  Los eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> también reciben un objeto <xref:System.Windows.Forms.DataGridViewCellStyle> de los datos de eventos, pero en este caso, es una copia de la propiedad <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> de fila de sólo lectura y cualquier cambio que se realice en ella no afecta al control.  
  
 También puede modificar dinámicamente los estilos de celdas individuales como respuesta a los eventos como <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=fullName> y <xref:System.Windows.Forms.DataGridView.CellMouseLeave>.  Por ejemplo, en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellMouseEnter>, podría almacenar el valor actual del color de fondo de celda \(recuperado mediante la propiedad<xref:System.Windows.Forms.DataGridViewCell.Style%2A> de la celda\) y establecerlo en un nuevo color que resalte la celda cuando el mouse se mantiene sobre ella.  En un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellMouseLeave> puede restablecer el color de fondo al valor original.  
  
> [!NOTE]
>  Almacenar en memoria caché los valores almacenados en la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A> de la celda es importante independientemente de si se establece un valor de estilo determinado.  Si reemplaza temporalmente un valor de estilo, restablecerlo a su estado original "no establecido" garantiza que la celda vuelva a heredar el valor de estilo del nivel más alto.  Si necesita determinar el estilo actual activado para una celda independientemente de si se hereda el estilo, utilice la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> de la celda.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Formato de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)