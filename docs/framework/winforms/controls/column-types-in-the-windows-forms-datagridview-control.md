---
title: "Tipos de columnas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], tipos"
  - "cuadrículas de datos, columnas"
  - "DataGridView (control) [Windows Forms], tipos de columna"
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Tipos de columnas en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> utiliza varios tipos de columna para mostrar información y permitir a los usuarios modificarla o agregarla.  
  
 Cuando se enlaza un control <xref:System.Windows.Forms.DataGridView> y se establece la propiedad <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> en `true`, las columnas se generan automáticamente mediante los tipos de columna predeterminados, adecuados a los tipos de datos contenidos en los orígenes de datos enlazados.  
  
 También se pueden crear instancias de cualquier clase de columna y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A>.  Se pueden crear estas instancias para utilizarlas como columnas sin enlazar o se pueden enlazar manualmente.  Por ejemplo, las columnas enlazadas manualmente resultan muy útiles cuando se quiere reemplazar una columna de un tipo, generada automáticamente, con una columna de otro tipo.  
  
 En la tabla siguiente se describen las distintas clases de columnas disponibles para su uso en el control <xref:System.Windows.Forms.DataGridView>.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Se utiliza con valores basados en texto.  Se genera automáticamente al enlazarse a los números y cadenas.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Se utiliza con valores <xref:System.Boolean> y <xref:System.Windows.Forms.CheckState>.  Se genera automáticamente al enlazarse a valores de estos tipos.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Se utiliza para mostrar imágenes.  Se genera automáticamente al enlazarse a las matrices de bytes, objetos <xref:System.Drawing.Image> o bien objetos <xref:System.Drawing.Icon>.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Se utiliza para mostrar botones en las celdas.  No se genera automáticamente al crear el enlace.  Normalmente se utiliza como columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Se utiliza para mostrar las listas desplegables en celdas.  No se genera automáticamente al crear el enlace.  Normalmente, se enlazan a datos manualmente.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Se utiliza para mostrar vínculos en las celdas.  No se genera automáticamente al crear el enlace.  Normalmente, se enlazan a datos manualmente.|  
|El tipo de columna personalizado|Puede crear su propia clase de columnas que heredan la clase <xref:System.Windows.Forms.DataGridViewColumn> o cualquiera de sus clases derivadas para proporcionar una apariencia o un comportamiento personalizados, o controles hospedados.  Para obtener más información, vea [Cómo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).|  
  
 En las secciones siguientes se describen estos tipos de columna de forma más detallada.  
  
## DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> es un tipo de columna de propósito general para su uso con valores basados en texto, como números y cadenas.  En modo de edición, se muestra un control <xref:System.Windows.Forms.TextBox> en la celda activa que permite a los usuarios modificar el valor de la celda.  
  
 Los valores de la celda se convierten automáticamente en cadenas que se van a mostrar.  Los valores especificados o modificados por el usuario se analizan de forma automática para crear un valor de celda del tipo de datos adecuado.  Puede personalizar estas conversiones mediante el control de los eventos <xref:System.Windows.Forms.DataGridView.CellFormatting> y <xref:System.Windows.Forms.DataGridView.CellParsing> del control <xref:System.Windows.Forms.DataGridView>.  
  
 El tipo de datos del valor de celda de una columna se especifica en la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> de la columna.  
  
## DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> se utiliza con valores <xref:System.Boolean> y <xref:System.Windows.Forms.CheckState>.  Los valores <xref:System.Boolean> se muestran como casillas de dos o tres estados, según el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>.  Cuando la columna se enlaza a los valores de <xref:System.Windows.Forms.CheckState>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> es `true` de manera predeterminada.  
  
 Normalmente, los valores de celda de la casilla están pensados para el almacenamiento, como cualquier otro dato, o para realizar las operaciones masivas.  Si desea responder inmediatamente cuando los usuarios hacen clic en una celda de una casilla, puede controlar el evento <xref:System.Windows.Forms.DataGridView.CellClick>, pero este evento se produce antes de que se actualice el valor de la celda.  Si necesita el nuevo valor en el momento del clic, una de las opciones es calcular que el valor esperado se basará en el valor actual.  Otro enfoque es confirmar inmediatamente el cambio y controlar el evento <xref:System.Windows.Forms.DataGridView.CellValueChanged> para responder a él.  Para confirmar el cambio cuando se hace clic en la celda, debe controlar el evento <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged>.  En el controlador, si la celda actual es una celda de la casilla, llame al método <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> y pase el valor <xref:System.Windows.Forms.DataGridViewDataErrorContexts>.  
  
## DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn> se utiliza para mostrar imágenes.  Las columnas de imágenes se pueden rellenar automáticamente desde un origen de datos, rellenar manualmente para columnas sin enlazar o bien dinámicamente en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 El rellenado automático de una columna de imágenes desde un origen de datos funciona con matrices de bytes en una variedad de formatos de imagen, incluso todos los formatos que admiten la clase <xref:System.Drawing.Image> y el formato OLE Picture utilizado por Microsoft® Access y la base de datos de ejemplo Northwind.  
  
 El rellenado manual de una columna de imagen resulta muy útil cuando se desea proporcionar la funcionalidad de <xref:System.Windows.Forms.DataGridViewButtonColumn>, pero con un aspecto personalizado.  Puede controlar el evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName> para responder a los clics dentro de una celda de imagen.  
  
 El rellenado de las celdas de una columna de imagen en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting> resulta muy útil cuando se desea proporcionar imágenes para valores calculados o valores en formatos que no sean de imagen.  Por ejemplo, puede tener una columna "Riesgo" con valores de cadena como `"high"`, `"middle"` y `"low"`, que desea mostrar como iconos.  Otra posibilidad es tener una columna "Imagen" que contiene las ubicaciones de las imágenes que deben cargarse en lugar de su contenido binario.  
  
## DataGridViewButtonColumn  
 Con <xref:System.Windows.Forms.DataGridViewButtonColumn> puede mostrar una columna de celdas que contienen botones.  Esto es útil cuando desea facilitar a los usuarios la realización de acciones en registros determinados, tales como colocar un orden o mostrar registros secundarios en otra ventana.  
  
 Las columnas de botón no se generan automáticamente cuando se enlaza a datos un <xref:System.Windows.Forms.DataGridView>.  Para utilizar las columnas de botón, debe crearlas manualmente y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>.  
  
 Puede responder a los clics del usuario en celdas de botón mediante el control del evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>.  
  
## DataGridViewComboBoxColumn  
 Con <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, puede mostrar una columna de celdas que contiene los cuadros de lista desplegables.  Esto es útil para la entrada de datos en campos que sólo pueden contener valores determinados, como la columna Category de la tabla Products en la base de datos de ejemplo Northwind.  
  
 Se puede rellenar la lista desplegable utilizada para todas las celdas de la misma forma que se rellenaría una lista desplegable de <xref:System.Windows.Forms.ComboBox>, ya sea manualmente a partir de la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>, o enlazándola a un origen de datos a través de las propiedades <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.  Para obtener más información, vea [ComboBox \(Control\)](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md).  
  
 Se pueden enlazar los valores de celda reales al origen de datos utilizado por el control <xref:System.Windows.Forms.DataGridView> estableciendo la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> de <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName>.  
  
 Las columnas de cuadro combinado no se generan automáticamente cuando se enlaza a datos un <xref:System.Windows.Forms.DataGridView>.  Para utilizar las columnas de cuadro combinado, debe crearlas manualmente y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
## DataGridViewLinkColumn  
 Con <xref:System.Windows.Forms.DataGridViewLinkColumn> puede mostrar una columna de celdas que contienen hipervínculos.  Esto es útil para los valores de direcciones URL en el origen de datos o como alternativa a la columna de botón si se desean comportamientos especiales, como la apertura de una ventana con registros secundarios.  
  
 Las columnas de vínculo no se generan automáticamente cuando se enlaza a datos un <xref:System.Windows.Forms.DataGridView>.  Para utilizar las columnas de vínculo, debe crearlas manualmente y agregarlas a la colección devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
 Puede responder a los clics del usuario en vínculos mediante el control del evento <xref:System.Windows.Forms.DataGridView.CellContentClick>.  Este evento es distinto de los eventos <xref:System.Windows.Forms.DataGridView.CellClick> y <xref:System.Windows.Forms.DataGridView.CellMouseClick>, que aparecen cuando un usuario hace clic en cualquier parte en una celda.  
  
 La clase <xref:System.Windows.Forms.DataGridViewLinkColumn> proporciona varias propiedades para modificar el aspecto de vínculos antes, durante y después de haber hecho clic.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewButtonColumn>   
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewImageColumn>   
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewLinkColumn>   
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Cómo: Mostrar imágenes en celdas del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)   
 [Cómo: Trabajar con columnas de imágenes en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)   
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)