---
title: Modos de selección en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: c512a296f618ab32781dd8718a47c4b20fd7f54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745914"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modos de selección en el control DataGridView de formularios Windows Forms
A veces desea que su aplicación para realizar acciones según las selecciones del usuario dentro de un <xref:System.Windows.Forms.DataGridView> control. Dependiendo de las acciones, puede restringir los tipos de selección que son posibles. Por ejemplo, suponga que la aplicación puede imprimir un informe para el registro seleccionado actualmente. En este caso, es posible que desee configurar el <xref:System.Windows.Forms.DataGridView> control para que al hacer clic en cualquier lugar dentro de una fila siempre selecciona la fila completa y, por lo que se puede seleccionar que sólo una fila a la vez.  
  
 Puede especificar las selecciones permitidas estableciendo el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad en uno de los siguientes <xref:System.Windows.Forms.DataGridViewSelectionMode> valores de enumeración.  
  
|Valor de DataGridViewSelectionMode|Descripción|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Haga clic en una celda se selecciona. Encabezados de columna y fila no se puede usar para la selección.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Haga clic en una celda se selecciona. Al hacer clic en un encabezado de columna, se selecciona toda la columna. No se puede usar los encabezados de columna para ordenar.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Al hacer clic en una celda o un encabezado de columna, se selecciona toda la columna. No se puede usar los encabezados de columna para ordenar.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Al hacer clic en una celda o un encabezado de fila, se selecciona toda la fila.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modo de selección de forma predeterminada. Haga clic en una celda se selecciona. Al hacer clic en un encabezado de fila, se selecciona toda la fila.|  
  
> [!NOTE]
>  Cambiar automáticamente el modo de selección en tiempo de ejecución, borra la selección actual.  
  
 De forma predeterminada, los usuarios pueden seleccionar varias filas, columnas o celdas arrastrando con el mouse, al presionar la tecla CTRL o MAYÚS al seleccionar la opción para ampliar o modificar una selección o al hacer clic en la celda de encabezado de la parte superior izquierda para seleccionar todas las celdas del control. Para evitar este comportamiento, establezca el <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad `false`.  
  
 El <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> y <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> los modos permiten que los usuarios eliminar filas seleccionándolos y presionando la tecla SUPR. Los usuarios pueden eliminar las filas solo cuando la celda actual no está en modo de edición, el <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> propiedad está establecida en `true`, y el origen de datos subyacente admite la eliminación de fila controlado por el usuario. Tenga en cuenta que esta configuración no impide la eliminación de fila mediante programación.  
  
## <a name="programmatic-selection"></a>Selección mediante programación  
 El modo de selección actual limita el comportamiento de selección mediante programación, así como la selección del usuario. La selección actual se puede cambiar mediante programación estableciendo la `Selected` propiedad de las celdas, filas o columnas presentes en el <xref:System.Windows.Forms.DataGridView> control. También puede seleccionar todas las celdas del control a través de la <xref:System.Windows.Forms.DataGridView.SelectAll%2A> método, según el modo de selección. Para borrar la selección, use el <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> método.  
  
 Si el <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad está establecida en `true`, puede agregar <xref:System.Windows.Forms.DataGridView> elementos o quitarlos de la selección cambiando el `Selected` propiedad del elemento. En caso contrario, establecer el `Selected` propiedad `true` para un elemento quita automáticamente otros elementos de la selección.  
  
 Tenga en cuenta que al cambiar el valor de la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad, no modifica la selección actual.  
  
 Puede recuperar una colección de las celdas seleccionadas, filas o columnas a través de la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> propiedades de la <xref:System.Windows.Forms.DataGridView> control. Acceso a estas propiedades es ineficaz cuando se selecciona todas las celdas del control. Para evitar una reducción del rendimiento en este caso, use el <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método primero. Además, tener acceso a estas colecciones para determinar el número de celdas seleccionadas, filas o columnas pueden ser ineficaz. En su lugar, debe usar el <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> método, pasando el <xref:System.Windows.Forms.DataGridViewElementStates.Selected> valor.  
  
> [!TIP]
>  Código de ejemplo que muestra el uso de las celdas seleccionadas mediante programación puede encontrarse en el <xref:System.Windows.Forms.DataGridView> información general de clases.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer el modo de selección del Control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
