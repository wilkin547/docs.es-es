---
title: Tipos de columnas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: a33cf4cd865921c04ef10c7fccf3a67c3d22de73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956252"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Tipos de columnas en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control usa varios tipos de columna para mostrar su información y permitir que los usuarios modificar o agregar información.  
  
 Al enlazar un <xref:System.Windows.Forms.DataGridView> control y establezca el <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> propiedad `true`, se generan automáticamente columnas con tipos de columna predeterminados adecuados para los tipos de datos contenidos en el origen de datos enlazado.  
  
 También puede crear instancias de cualquiera de las clases de columna por sí mismo y agregarlos a la colección devuelta por la <xref:System.Windows.Forms.DataGridView.Columns%2A> propiedad. Puede crear estas instancias para su uso como columnas sin enlazar o se pueden enlazar manualmente. Las columnas enlazadas manualmente son útiles, por ejemplo, cuando desea reemplazar una columna de un tipo generado automáticamente por una columna de otro tipo.  
  
 La tabla siguiente describen las distintas clases de columna disponibles para su uso en el <xref:System.Windows.Forms.DataGridView> control.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Se usa con valores basados en texto. Se genera automáticamente cuando se enlaza a números y cadenas.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Puede usar con <xref:System.Boolean> y <xref:System.Windows.Forms.CheckState> valores. Se genera automáticamente cuando se enlazan a los valores de estos tipos.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Se usa para mostrar imágenes. Genera automáticamente cuando se enlazan a las matrices de bytes, <xref:System.Drawing.Image> objetos, o <xref:System.Drawing.Icon> objetos.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Se utiliza para mostrar botones en las celdas. No se genera automáticamente cuando se enlaza. Normalmente se utilizan como columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Se utiliza para mostrar listas desplegables en las celdas. No se genera automáticamente cuando se enlaza. Normalmente, enlazados a datos manualmente.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Se usa para mostrar los vínculos de las celdas. No se genera automáticamente cuando se enlaza. Normalmente, enlazados a datos manualmente.|  
|El tipo de columna personalizada|Puede crear su propia clase de columna heredando la <xref:System.Windows.Forms.DataGridViewColumn> clase o cualquiera de sus clases derivadas para proporcionar una apariencia personalizada, comportamiento o controles hospedados. Para obtener más información, vea [Cómo: Personalizar celdas y columnas en el Control DataGridView de Windows Forms ampliando su comportamiento y apariencia](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Estos tipos de columna se describen con más detalle en las secciones siguientes.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 El <xref:System.Windows.Forms.DataGridViewTextBoxColumn> es un tipo de columna de propósito general para su uso con valores basados en texto tales como números y cadenas. En modo de edición, un <xref:System.Windows.Forms.TextBox> control se muestra en la celda activa, lo que permite a los usuarios modificar el valor de celda.  
  
 Los valores de celda se convierten automáticamente en cadenas para mostrar. Los valores especificados o modificados por el usuario se analizan automáticamente para crear un valor de celda del tipo de datos adecuado. Puede personalizar estas conversiones controlando el <xref:System.Windows.Forms.DataGridView.CellFormatting> y <xref:System.Windows.Forms.DataGridView.CellParsing> eventos de la <xref:System.Windows.Forms.DataGridView> control.  
  
 El tipo de datos del valor de celda de una columna se especifica en el <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> propiedad de la columna.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 El <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> se usa con <xref:System.Boolean> y <xref:System.Windows.Forms.CheckState> valores. <xref:System.Boolean> los valores se muestran como casillas de verificación de dos o tres estados, dependiendo del valor de la <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> propiedad. Cuando la columna se enlaza a <xref:System.Windows.Forms.CheckState> valores, el <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> es el valor de propiedad `true` de forma predeterminada.  
  
 Normalmente, los valores de celda de la casilla de verificación están pensados para el almacenamiento, como cualquier otro dato, o para realizar operaciones masivas. Si desea responder inmediatamente cuando los usuarios, haga clic en una celda de la casilla de verificación, puede controlar la <xref:System.Windows.Forms.DataGridView.CellClick> eventos, pero este evento se produce antes de actualiza el valor de celda. Si necesita el nuevo valor en el momento de hacer clic en, es una opción calcular cuál será el valor esperado en función del valor actual. Otro enfoque consiste en confirmar el cambio inmediatamente y controlar el <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventos para responder a él. Para confirmar el cambio cuando se hace clic en la celda, se debe controlar la <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> eventos. En el controlador, si la celda actual es una celda de la casilla de verificación, llame a la <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> método y pase la <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> valor.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 El <xref:System.Windows.Forms.DataGridViewImageColumn> se usa para mostrar imágenes. Columnas de imagen se rellena automáticamente desde un origen de datos, rellenar manualmente para columnas sin enlazar o rellena dinámicamente en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos.  
  
 El rellenado automático de una columna de imagen desde un origen de datos funciona con las matrices de bytes en una variedad de formatos de imagen, incluidos todos los formatos admitidos por el <xref:System.Drawing.Image> clase y el formato de imagen OLE utilizado por Microsoft® Access y la base de datos de ejemplo Northwind.  
  
 Rellenar manualmente una columna de imagen es útil cuando desea proporcionar la funcionalidad de un <xref:System.Windows.Forms.DataGridViewButtonColumn>, pero con un aspecto personalizado. Puede controlar la <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> eventos para responder a clics en una celda de la imagen.  
  
 Rellenar las celdas de una columna de imagen en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting> evento es útil cuando desea proporcionar imágenes para valores calculados o valores en formatos de imagen no. Por ejemplo, puede tener una columna "Riesgo" con valores de cadena como `"high"`, `"middle"`, y `"low"` que desea mostrar como iconos. Como alternativa, puede tener una columna de "Imagen" que contiene las ubicaciones de las imágenes que deben cargarse en lugar de contenido binario de las imágenes.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Con el <xref:System.Windows.Forms.DataGridViewButtonColumn>, puede mostrar una columna de celdas que contienen botones. Esto es útil cuando desea proporcionar una manera fácil para los usuarios realizar acciones en los registros determinados, como realizar un pedido o mostrar registros secundarios en una ventana independiente.  
  
 Columnas de botones no se generan automáticamente cuando el enlace de datos un <xref:System.Windows.Forms.DataGridView> control. Para usar las columnas de botón, debe crearlas manualmente y agregarlas a la colección devuelta por la <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> propiedad.  
  
 Puede responder a clics de usuario en las celdas de botón controlando el <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> eventos.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Con el <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, puede mostrar una columna de celdas que contienen los cuadros de lista desplegable. Esto es útil para la entrada de datos en los campos que puede contener solo valores determinados, como la columna de categoría de la tabla Products de la base de datos de ejemplo Northwind.  
  
 Puede rellenar la lista desplegable que se usa para todas las celdas de la misma manera que rellenaría un <xref:System.Windows.Forms.ComboBox> la lista desplegable, ya sea manualmente a través de la colección devuelta por la <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> propiedad, o enlazándola a un origen de datos a través de la <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> propiedades. Para obtener más información, consulte [ComboBox Control](combobox-control-windows-forms.md).  
  
 Puede enlazar los valores de celda real al origen de datos utilizado por el <xref:System.Windows.Forms.DataGridView> control estableciendo el <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Columnas de cuadro combinado no se generan automáticamente cuando el enlace de datos un <xref:System.Windows.Forms.DataGridView> control. Para usar las columnas de cuadro combinado, debe crearlas manualmente y agregarlas a la colección devuelta por la <xref:System.Windows.Forms.DataGridView.Columns%2A> propiedad.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Con el <xref:System.Windows.Forms.DataGridViewLinkColumn>, puede mostrar una columna de celdas que contienen hipervínculos. Esto es útil para los valores de dirección URL del origen de datos o como alternativa a la columna de botones para comportamientos especiales, como abrir una ventana con los registros secundarios.  
  
 Las columnas de vínculo no se generan automáticamente cuando el enlace de datos un <xref:System.Windows.Forms.DataGridView> control. Para usar las columnas de vínculo, debe crearlas manualmente y agregarlas a la colección devuelta por la <xref:System.Windows.Forms.DataGridView.Columns%2A> propiedad.  
  
 Puede responder a clics de usuario en los vínculos controlando el <xref:System.Windows.Forms.DataGridView.CellContentClick> eventos. Este evento es distinto de la <xref:System.Windows.Forms.DataGridView.CellClick> y <xref:System.Windows.Forms.DataGridView.CellMouseClick> eventos, que se producen cuando un usuario hace clic en cualquier parte en una celda.  
  
 La <xref:System.Windows.Forms.DataGridViewLinkColumn> clase proporciona varias propiedades para modificar la apariencia de vínculos antes, durante y después se hace clic en.  
  
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
- [Cómo: Mostrar imágenes en celdas del Control DataGridView de formularios Windows Forms](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [Cómo: Trabajar con columnas de imagen en el Control DataGridView de Windows Forms](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
