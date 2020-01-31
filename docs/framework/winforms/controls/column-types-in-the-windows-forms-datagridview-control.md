---
title: Tipos de columna en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: e918394cca6350854074d4c1567890138b2a1462
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743852"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Tipos de columnas en el control DataGridView de Windows Forms
El control <xref:System.Windows.Forms.DataGridView> utiliza varios tipos de columna para mostrar su información y permitir que los usuarios modifiquen o agreguen información.  
  
 Al enlazar un control de <xref:System.Windows.Forms.DataGridView> y establecer la propiedad <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> en `true`, las columnas se generan automáticamente utilizando los tipos de columna predeterminados adecuados para los tipos de datos incluidos en el origen de datos enlazado.  
  
 También puede crear instancias de cualquiera de las clases de columna y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A>. Puede crear estas instancias para utilizarlas como columnas sin enlazar, o puede enlazarlas manualmente. Las columnas enlazadas manualmente son útiles, por ejemplo, cuando se desea reemplazar una columna generada automáticamente de un tipo con una columna de otro tipo.  
  
 En la tabla siguiente se describen las distintas clases de columna disponibles para su uso en el control <xref:System.Windows.Forms.DataGridView>.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Se utiliza con valores basados en texto. Se genera automáticamente al enlazar a números y cadenas.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Se utiliza con valores <xref:System.Boolean> y <xref:System.Windows.Forms.CheckState>. Se genera automáticamente al enlazar a valores de estos tipos.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Se utiliza para mostrar imágenes. Se generan automáticamente al enlazar a matrices de bytes, objetos <xref:System.Drawing.Image> o objetos <xref:System.Drawing.Icon>.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Se usa para mostrar botones en las celdas. No se genera automáticamente al enlazar. Se utiliza normalmente como columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Se usa para mostrar listas desplegables en las celdas. No se genera automáticamente al enlazar. Normalmente enlazado a datos de forma manual.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Se utiliza para mostrar los vínculos en las celdas. No se genera automáticamente al enlazar. Normalmente enlazado a datos de forma manual.|  
|El tipo de columna personalizado|Puede crear su propia clase de columna heredando la clase <xref:System.Windows.Forms.DataGridViewColumn> o cualquiera de sus clases derivadas para proporcionar la apariencia, el comportamiento o los controles hospedados personalizados. Para obtener más información, vea [Cómo: personalizar celdas y columnas en el Control Windows Forms DataGridView extendiendo su comportamiento y apariencia](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Estos tipos de columna se describen con más detalle en las secciones siguientes.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 El <xref:System.Windows.Forms.DataGridViewTextBoxColumn> es un tipo de columna de uso general que se utiliza con valores basados en texto, como números y cadenas. En el modo de edición, se muestra un control <xref:System.Windows.Forms.TextBox> en la celda activa, lo que permite a los usuarios modificar el valor de la celda.  
  
 Los valores de celda se convierten automáticamente en cadenas para su presentación. Los valores especificados o modificados por el usuario se analizan automáticamente para crear un valor de celda con el tipo de datos adecuado. Puede personalizar estas conversiones controlando los eventos <xref:System.Windows.Forms.DataGridView.CellFormatting> y <xref:System.Windows.Forms.DataGridView.CellParsing> del control <xref:System.Windows.Forms.DataGridView>.  
  
 El tipo de datos del valor de celda de una columna se especifica en la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> de la columna.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 El <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> se utiliza con los valores <xref:System.Boolean> y <xref:System.Windows.Forms.CheckState>. <xref:System.Boolean> valores se muestran como casillas de dos o tres Estados, dependiendo del valor de la propiedad <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>. Cuando la columna está enlazada a <xref:System.Windows.Forms.CheckState> valores, el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> se `true` de forma predeterminada.  
  
 Normalmente, los valores de las celdas de las casillas están pensados para el almacenamiento, como cualquier otro dato, o para realizar operaciones masivas. Si desea responder inmediatamente cuando los usuarios hacen clic en una celda de casilla, puede controlar el evento <xref:System.Windows.Forms.DataGridView.CellClick>, pero este evento se produce antes de que se actualice el valor de la celda. Si necesita el nuevo valor en el momento del clic, una opción es calcular cuál será el valor esperado basándose en el valor actual. Otro enfoque consiste en confirmar el cambio inmediatamente y controlar el evento <xref:System.Windows.Forms.DataGridView.CellValueChanged> para responder a él. Para confirmar el cambio cuando se hace clic en la celda, debe controlar el evento <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged>. En el controlador, si la celda actual es una celda de casilla, llame al método <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> y pase el valor de <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit>.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 El <xref:System.Windows.Forms.DataGridViewImageColumn> se utiliza para mostrar imágenes. Las columnas de imagen se pueden rellenar automáticamente a partir de un origen de datos, rellenar manualmente para columnas sin enlazar o rellenar dinámicamente en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 El rellenado automático de una columna de imagen a partir de un origen de datos funciona con matrices de bytes en una variedad de formatos de imagen, incluidos todos los formatos admitidos por la clase <xref:System.Drawing.Image> y el formato de imagen OLE utilizado por Microsoft® Access y la base de datos de ejemplo Northwind.  
  
 Rellenar manualmente una columna de imagen es útil cuando desea proporcionar la funcionalidad de una <xref:System.Windows.Forms.DataGridViewButtonColumn>, pero con una apariencia personalizada. Puede controlar el evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> para responder a los clics dentro de una celda de imagen.  
  
 Rellenar las celdas de una columna de imagen en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting> resulta útil si desea proporcionar imágenes para valores calculados o valores en formatos que no son de imagen. Por ejemplo, puede tener una columna "riesgo" con valores de cadena como `"high"`, `"middle"`y `"low"` que desea mostrar como iconos. Como alternativa, puede tener una columna "imagen" que contenga las ubicaciones de las imágenes que se deben cargar en lugar del contenido binario de las imágenes.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Con el <xref:System.Windows.Forms.DataGridViewButtonColumn>, puede mostrar una columna de celdas que contengan botones. Esto resulta útil si desea proporcionar a los usuarios una forma sencilla de realizar acciones en determinados registros, como colocar un orden o mostrar los registros secundarios en una ventana independiente.  
  
 Las columnas de botón no se generan automáticamente cuando se enlazan datos a un control de <xref:System.Windows.Forms.DataGridView>. Para usar columnas de botón, debe crearlas manualmente y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>.  
  
 Puede responder a los clics del usuario en las celdas del botón controlando el evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Con el <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, puede mostrar una columna de celdas que contengan cuadros de lista desplegables. Esto resulta útil para la entrada de datos en campos que solo pueden contener valores concretos, como la columna categoría de la tabla productos de la base de datos de ejemplo Northwind.  
  
 Puede rellenar la lista desplegable que se usa para todas las celdas de la misma manera que rellenaría una lista desplegable de <xref:System.Windows.Forms.ComboBox>, ya sea manualmente a través de la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> o enlazándolo a un origen de datos a través de las propiedades <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. Para obtener más información, vea [ComboBox (control](combobox-control-windows-forms.md)).  
  
 Puede enlazar los valores de celda reales con el origen de datos utilizado por el control <xref:System.Windows.Forms.DataGridView> estableciendo la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> de la <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Las columnas de cuadro combinado no se generan automáticamente cuando se enlazan datos a un control de <xref:System.Windows.Forms.DataGridView>. Para utilizar columnas de cuadro combinado, debe crearlas manualmente y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Con el <xref:System.Windows.Forms.DataGridViewLinkColumn>, puede mostrar una columna de celdas que contengan hipervínculos. Esto resulta útil para los valores de dirección URL del origen de datos o como una alternativa a la columna Button para comportamientos especiales como abrir una ventana con registros secundarios.  
  
 Las columnas de vínculo no se generan automáticamente cuando se enlazan datos a un control de <xref:System.Windows.Forms.DataGridView>. Para usar las columnas de vínculo, debe crearlas manualmente y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
 Puede responder a los clics del usuario en los vínculos controlando el evento <xref:System.Windows.Forms.DataGridView.CellContentClick>. Este evento es distinto de los eventos <xref:System.Windows.Forms.DataGridView.CellClick> y <xref:System.Windows.Forms.DataGridView.CellMouseClick>, que se producen cuando un usuario hace clic en cualquier parte de una celda.  
  
 La clase <xref:System.Windows.Forms.DataGridViewLinkColumn> proporciona varias propiedades para modificar la apariencia de los vínculos antes, durante y después de que se haga clic en ellos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Cómo: Mostrar imágenes en celdas del control DataGridView de Windows Forms](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [Trabajar con columnas de imágenes en el control DataGridView de formularios Windows Forms](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
