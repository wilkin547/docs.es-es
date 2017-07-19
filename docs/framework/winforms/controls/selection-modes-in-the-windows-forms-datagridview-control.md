---
title: "Modos de selecci&#243;n en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "DataGridView (control) [Windows Forms], modo de selección"
  - "selección, modos en el control DataGridView"
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Modos de selecci&#243;n en el control DataGridView de formularios Windows Forms
A veces deseará que la aplicación realice acciones según las selecciones del usuario dentro de un control <xref:System.Windows.Forms.DataGridView>.  En función de las acciones, puede desear limitar los tipos de selección permitidos.  Por ejemplo, suponga que la aplicación puede imprimir un informe para el registro actualmente seleccionado.  En este caso, quizá desee configurar el control <xref:System.Windows.Forms.DataGridView> de modo que al hacer clic con el mouse en cualquier posición dentro de una fila siempre se seleccione la fila completa y que sólo se pueda seleccionar una fila a la vez.  
  
 Para especificar las selecciones permitidas establezca la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> en uno de los valores de la enumeración <xref:System.Windows.Forms.DataGridViewSelectionMode> siguientes.  
  
|Valor de DataGridViewSelectionMode|Descripción|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Si hace clic en una celda se selecciona.  Los encabezados de fila y columna no se pueden utilizar para la selección.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Si hace clic en una celda se selecciona.  Al hacer clic en un encabezado de columna, se selecciona la columna completa.  Los encabezados de columna no se pueden utilizar para ordenar.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Al hacer clic en un un encabezado de celda o columna se selecciona la columna completa.  Los encabezados de columna no se pueden utilizar para ordenar.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Al hacer clic en un encabezado de celda o fila se selecciona la fila completa.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Modo de selección predeterminado.  Si hace clic en una celda se selecciona.  Al hacer clic en un encabezado de fila, se selecciona la fila completa.|  
  
> [!NOTE]
>  Al cambiar el modo de selección en tiempo de ejecución, se borra automáticamente la selección actual.  
  
 De manera predeterminada, para seleccionar varias filas, columnas o celdas los usuarios arrastran con el mouse, presionan CTRL o MAYÚS mientras realizan la selección para ampliar o modificar la selección o hacen clic con el mouse en la celda de encabezado superior izquierda para seleccionar todas las celdas del control.  Para impedir este comportamiento, establezca la propiedad <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> en `false`.  
  
 Los modos <xref:System.Windows.Forms.DataGridViewSelectionMode> y <xref:System.Windows.Forms.DataGridViewSelectionMode> permiten que los usuarios eliminen filas seleccionándolas y presionando la tecla SUPR.  Los usuarios pueden eliminar filas sólo cuando la celda actual no está en el modo de edición, la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> está establecida en `true` y el origen de datos subyacente admite la eliminación de fila controlada por el usuario.  Observe que esta configuración no evita la eliminación de fila mediante programación.  
  
## Selección mediante programación  
 El modo de selección actual limita el comportamiento de la selección mediante programación así como la selección del usuario.  Puede cambiar mediante programación la selección actual estableciendo la propiedad `Selected` de cualquier celda, fila o columna presente en el control <xref:System.Windows.Forms.DataGridView>.  También puede seleccionar todas las celdas del control a través del método <xref:System.Windows.Forms.DataGridView.SelectAll%2A>, en función del modo de selección.  Para borrar la selección, utilice el método <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>.  
  
 Si la propiedad <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecida en `true`, puede agregar elementos <xref:System.Windows.Forms.DataGridView> o quitarlos de la selección cambiando la propiedad `Selected` del elemento.  De lo contrario, al establecer la propiedad `Selected` en `true` para un elemento, se quitarán  automáticamente otros elementos de la selección.  
  
 Observe que al cambiar el valor de la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>, no se modifica la selección actual.  
  
 Puede recuperar una colección de celdas, filas o columnas actualmente seleccionadas a través de las propiedades <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> del control <xref:System.Windows.Forms.DataGridView>.  El acceso a estas propiedades es ineficaz cuando se seleccionan todas las celdas del control.  Para evitar una reducción del rendimiento en este caso, utilice primero el método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>.  Además, tener acceso a estas colecciones para determinar el número de celdas, filas o columnas seleccionadas puede resultar ineficaz.  En su lugar, utilice el método <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>, con el valor <xref:System.Windows.Forms.DataGridViewElementStates> pasado como parámetro.  
  
> [!TIP]
>  Para obtener un código de ejemplo en el que se muestra el uso mediante programación de las celdas seleccionadas, vea la información general sobre la clase <xref:System.Windows.Forms.DataGridView>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridViewSelectionMode>   
 [Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer el modelo de selección del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)