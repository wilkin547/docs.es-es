---
title: Modos de selección en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: e20bf6307d77bf189b698e847c6b855c249dc3c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743042"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Modos de selección en el control DataGridView de formularios Windows Forms

A veces desea que la aplicación realice acciones en función de las selecciones de usuario dentro de un control de <xref:System.Windows.Forms.DataGridView>. En función de las acciones, puede que desee restringir los tipos de selección que son posibles. Por ejemplo, supongamos que la aplicación puede imprimir un informe para el registro seleccionado actualmente. En este caso, es posible que desee configurar el control <xref:System.Windows.Forms.DataGridView> de modo que al hacer clic en cualquier parte dentro de una fila, siempre se seleccione toda la fila, de modo que solo se pueda seleccionar una fila cada vez.

Puede especificar las selecciones que se permiten estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> en uno de los siguientes valores de enumeración de <xref:System.Windows.Forms.DataGridViewSelectionMode>.

|Valor DataGridViewSelectionMode|Descripción|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|Al hacer clic en una celda, se selecciona. Los encabezados de fila y de columna no se pueden usar para la selección.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|Al hacer clic en una celda, se selecciona. Al hacer clic en un encabezado de columna, se selecciona toda la columna. Los encabezados de columna no se pueden usar para la ordenación.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Al hacer clic en una celda o en un encabezado de columna, se selecciona toda la columna. Los encabezados de columna no se pueden usar para la ordenación.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Al hacer clic en una celda o en un encabezado de fila, se selecciona toda la fila.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Modo de selección predeterminada. Al hacer clic en una celda, se selecciona. Al hacer clic en un encabezado de fila, se selecciona toda la fila.|

> [!NOTE]
> Al cambiar el modo de selección en tiempo de ejecución, se borra automáticamente la selección actual.

De forma predeterminada, los usuarios pueden seleccionar varias filas, columnas o celdas arrastrando con el mouse, presionando CTRL o Mayús mientras seleccionan ampliar o modificar una selección, o haciendo clic en la celda del encabezado superior izquierdo para seleccionar todas las celdas del control. Para evitar este comportamiento, establezca la propiedad <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> en `false`.

Los modos <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> y <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> permiten a los usuarios eliminar filas seleccionándolos y presionando la tecla Supr. Los usuarios solo pueden eliminar filas si la celda actual no está en modo de edición, la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> está establecida en `true`y el origen de datos subyacente admite la eliminación de filas controlada por el usuario. Tenga en cuenta que esta configuración no impide la eliminación de filas mediante programación.

## <a name="programmatic-selection"></a>Selección mediante programación

El modo de selección actual restringe el comportamiento de la selección mediante programación, así como la selección del usuario. Puede cambiar la selección actual mediante programación estableciendo la propiedad `Selected` de las celdas, filas o columnas presentes en el control <xref:System.Windows.Forms.DataGridView>. También puede seleccionar todas las celdas del control a través del método <xref:System.Windows.Forms.DataGridView.SelectAll%2A>, dependiendo del modo de selección. Para borrar la selección, use el método <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>.

Si la propiedad <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecida en `true`, puede Agregar o quitar elementos <xref:System.Windows.Forms.DataGridView> de la selección cambiando la propiedad `Selected` del elemento. De lo contrario, al establecer la propiedad `Selected` en `true` para un elemento, se quitan automáticamente otros elementos de la selección.

Tenga en cuenta que al cambiar el valor de la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> no se modifica la selección actual.

Puede recuperar una colección de las celdas, filas o columnas seleccionadas actualmente a través de las propiedades <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> del control <xref:System.Windows.Forms.DataGridView>. El acceso a estas propiedades es ineficaz cuando se seleccionan todas las celdas del control. Para evitar una reducción del rendimiento en este caso, use primero el método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>. Además, el acceso a estas colecciones para determinar el número de celdas, filas o columnas seleccionadas puede ser ineficaz. En su lugar, debe usar el método <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>o <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>, pasando el valor de <xref:System.Windows.Forms.DataGridViewElementStates.Selected>.

> [!TIP]
> En la información general de la clase <xref:System.Windows.Forms.DataGridView> se puede encontrar código de ejemplo que muestra el uso mediante programación de las celdas seleccionadas.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Establecer el modelo de selección del control DataGridView de formularios Windows Forms](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
