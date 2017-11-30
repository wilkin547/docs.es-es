---
title: "Modos de selección en el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f6b603382382971249b08cddd482566ec6e5fa5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modos de selección en el control DataGridView de formularios Windows Forms
A veces, desea que la aplicación para realizar acciones en función de las selecciones del usuario dentro de un <xref:System.Windows.Forms.DataGridView> control. Dependiendo de las acciones, puede que desee restringir los tipos de selección que son posibles. Por ejemplo, suponga que la aplicación puede imprimir un informe para el registro seleccionado actualmente. En este caso, puede que desee configurar el <xref:System.Windows.Forms.DataGridView> control para que al hacer clic en cualquier lugar dentro de una fila siempre selecciona toda la fila y, por lo que se puede seleccionar que sólo una fila a la vez.  
  
 Puede especificar las selecciones permitidas estableciendo la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad en uno de los siguientes <xref:System.Windows.Forms.DataGridViewSelectionMode> valores de enumeración.  
  
|Valor de DataGridViewSelectionMode|Descripción|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Haga clic en una celda lo selecciona. Encabezados de fila y columna no se puede usar para la selección.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Haga clic en una celda lo selecciona. Al hacer clic en un encabezado de columna, se selecciona toda la columna. Encabezados de columna no se puede usar para la ordenación.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Haga clic en una celda o un encabezado de columna, se selecciona toda la columna. Encabezados de columna no se puede usar para la ordenación.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Haga clic en una celda o un encabezado de fila, se selecciona toda la fila.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modo de selección de forma predeterminada. Haga clic en una celda lo selecciona. Al hacer clic en un encabezado de fila, se selecciona toda la fila.|  
  
> [!NOTE]
>  Cambiar automáticamente el modo de selección en tiempo de ejecución, borra la selección actual.  
  
 De forma predeterminada, los usuarios pueden seleccionar varias filas, columnas o celdas arrastrando con el mouse, presionando la tecla CTRL o MAYÚS al seleccionar la opción para ampliar o modificar una selección o haga clic en la celda de encabezado superior izquierda para seleccionar todas las celdas del control. Para evitar este comportamiento, configure la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad `false`.  
  
 El <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> y <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> modos de permiten a los usuarios eliminar filas seleccionándolos y presionando la tecla SUPR. Los usuarios pueden eliminar filas sólo cuando la celda actual no está en modo de edición, el <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> propiedad está establecida en `true`, y el origen de datos subyacente admite la eliminación de fila controlada por el usuario. Tenga en cuenta que esta configuración no impiden la eliminación de fila mediante programación.  
  
## <a name="programmatic-selection"></a>Selección mediante programación  
 El modo de selección actual limita el comportamiento de selección mediante programación, así como la selección del usuario. Puede cambiar la selección actual mediante programación estableciendo la `Selected` propiedad de las celdas, filas o columnas presentes en el <xref:System.Windows.Forms.DataGridView> control. También puede seleccionar todas las celdas en el control mediante la <xref:System.Windows.Forms.DataGridView.SelectAll%2A> método, según el modo de selección. Para borrar la selección, use la <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> método.  
  
 Si el <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad está establecida en `true`, puede agregar <xref:System.Windows.Forms.DataGridView> elementos o quitarlos de la selección cambiando la `Selected` propiedad del elemento. En caso contrario, establecer el `Selected` propiedad `true` para un elemento quita automáticamente otros elementos de la selección.  
  
 Tenga en cuenta que, al cambiar el valor de la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad no modifica la selección actual.  
  
 Puede recuperar una colección de las celdas seleccionadas actualmente, filas o columnas a través de la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> propiedades de la <xref:System.Windows.Forms.DataGridView> control. Acceso a estas propiedades es ineficaz cuando se selecciona todas las celdas del control. Para evitar una reducción del rendimiento en este caso, use el <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método primero. Además, tener acceso a estas colecciones para determinar el número de celdas seleccionadas, filas o columnas pueden ser ineficaz. En su lugar, debe utilizar el <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> método, pasando el <xref:System.Windows.Forms.DataGridViewElementStates.Selected> valor.  
  
> [!TIP]
>  Código de ejemplo que muestra el uso de las celdas seleccionadas mediante programación puede encontrarse en el <xref:System.Windows.Forms.DataGridView> general sobre la clase.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [Establecer el modelo de selección del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
