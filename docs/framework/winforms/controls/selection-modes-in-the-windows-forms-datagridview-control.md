---
title: Modos de selección en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: cfe80d5ccb73208f1c61a2ac6c9963343d398bcb
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046417"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modos de selección en el control DataGridView de formularios Windows Forms

A veces desea que la aplicación realice acciones en función de las selecciones de <xref:System.Windows.Forms.DataGridView> usuario dentro de un control. En función de las acciones, puede que desee restringir los tipos de selección que son posibles. Por ejemplo, supongamos que la aplicación puede imprimir un informe para el registro seleccionado actualmente. En este caso, es posible que desee configurar el <xref:System.Windows.Forms.DataGridView> control de modo que al hacer clic en cualquier parte dentro de una fila, siempre se seleccione toda la fila, de modo que solo se pueda seleccionar una fila cada vez.

Puede especificar las selecciones que se permiten estableciendo la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad en uno de los siguientes <xref:System.Windows.Forms.DataGridViewSelectionMode> valores de enumeración.

|Valor DataGridViewSelectionMode|DESCRIPCIÓN|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Al hacer clic en una celda, se selecciona. Los encabezados de fila y de columna no se pueden usar para la selección.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Al hacer clic en una celda, se selecciona. Al hacer clic en un encabezado de columna, se selecciona toda la columna. Los encabezados de columna no se pueden usar para la ordenación.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Al hacer clic en una celda o en un encabezado de columna, se selecciona toda la columna. Los encabezados de columna no se pueden usar para la ordenación.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Al hacer clic en una celda o en un encabezado de fila, se selecciona toda la fila.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modo de selección predeterminada. Al hacer clic en una celda, se selecciona. Al hacer clic en un encabezado de fila, se selecciona toda la fila.|

> [!NOTE]
> Al cambiar el modo de selección en tiempo de ejecución, se borra automáticamente la selección actual.

De forma predeterminada, los usuarios pueden seleccionar varias filas, columnas o celdas arrastrando con el mouse, presionando CTRL o Mayús mientras seleccionan ampliar o modificar una selección, o haciendo clic en la celda del encabezado superior izquierdo para seleccionar todas las celdas del control. Para evitar este comportamiento, establezca la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad en `false`.

Los <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> modos <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> y permiten a los usuarios eliminar filas seleccionándolos y presionando la tecla Supr. Los usuarios solo pueden eliminar filas si la celda actual no está en modo de edición <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> , la propiedad se `true`establece en y el origen de datos subyacente admite la eliminación de filas controlada por el usuario. Tenga en cuenta que esta configuración no impide la eliminación de filas mediante programación.

## <a name="programmatic-selection"></a>Selección mediante programación

El modo de selección actual restringe el comportamiento de la selección mediante programación, así como la selección del usuario. Puede cambiar la selección actual mediante programación estableciendo la `Selected` propiedad de las celdas, filas o columnas presentes en el <xref:System.Windows.Forms.DataGridView> control. También puede seleccionar todas las celdas del control a través del <xref:System.Windows.Forms.DataGridView.SelectAll%2A> método, dependiendo del modo de selección. Para borrar la selección, use el <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> método.

Si la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad se establece en `true`, puede agregar <xref:System.Windows.Forms.DataGridView> o quitar elementos de la selección cambiando la `Selected` propiedad del elemento. De lo contrario, `Selected` si se `true` establece la propiedad en para un elemento, se quitan automáticamente otros elementos de la selección.

Tenga en cuenta que al cambiar el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> valor de la propiedad no se modifica la selección actual.

Puede recuperar una colección de las celdas, filas o columnas seleccionadas actualmente a través de las <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>propiedades <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> del <xref:System.Windows.Forms.DataGridView> control. El acceso a estas propiedades es ineficaz cuando se seleccionan todas las celdas del control. Para evitar una reducción del rendimiento en este caso, use <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> primero el método. Además, el acceso a estas colecciones para determinar el número de celdas, filas o columnas seleccionadas puede ser ineficaz. En su lugar, debe usar el <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>método <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> , pasando el <xref:System.Windows.Forms.DataGridViewElementStates.Selected> valor.

> [!TIP]
> En la información general de la <xref:System.Windows.Forms.DataGridView> clase se puede encontrar código de ejemplo que muestra el uso mediante programación de las celdas seleccionadas.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Procedimientos: Establecer el modo de selección del control DataGridView Windows Forms](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
