---
title: Obtener acceso a los objetos en la lista desplegable DataGridViewComboBoxCell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746314"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Cómo: Obtener acceso a objetos de una lista desplegable DataGridViewComboBoxCell en Windows Forms
Al igual que el control <xref:System.Windows.Forms.ComboBox>, los tipos <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y <xref:System.Windows.Forms.DataGridViewComboBoxCell> permiten agregar objetos arbitrarios a sus listas desplegables. Con esta característica, puede representar Estados complejos en una lista desplegable sin tener que almacenar los objetos correspondientes en una colección independiente.  
  
 A diferencia del control de <xref:System.Windows.Forms.ComboBox>, los tipos de <xref:System.Windows.Forms.DataGridView> no tienen una propiedad <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> para recuperar el objeto actualmente seleccionado. En su lugar, debe establecer la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> en el nombre de una propiedad del objeto comercial. Cuando el usuario realiza una selección, la propiedad indicada del objeto comercial establece la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad.  
  
 Para recuperar el objeto comercial a través del valor de la celda, la propiedad `ValueMember` debe indicar una propiedad que devuelva una referencia al propio objeto comercial. Por consiguiente, si el tipo del objeto comercial no está bajo el control, debe agregar este tipo de propiedad extendiendo el tipo a través de la herencia.  
  
 Los procedimientos siguientes muestran cómo rellenar una lista desplegable con objetos comerciales y recuperar los objetos a través de la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Para agregar objetos comerciales a la lista desplegable  
  
1. Cree una nueva <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y rellene su colección <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>. Como alternativa, puede establecer la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> de la columna en la colección de objetos comerciales. Sin embargo, en ese caso, no se puede Agregar "sin asignar" a la lista desplegable sin crear un objeto comercial correspondiente en la colección.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. Establezca las propiedades <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la propiedad del objeto comercial que se va a mostrar en la lista desplegable. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la propiedad que devuelve una referencia al objeto comercial.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. Asegúrese de que el tipo de objeto de negocio contiene una propiedad que devuelve una referencia a la instancia actual. Esta propiedad se debe denominar con el valor asignado a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> en el paso anterior.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Para recuperar el objeto comercial seleccionado actualmente  
  
- Obtiene la propiedad <xref:System.Windows.Forms.DataGridViewCell.Value%2A> de la celda y la convierte al tipo de objeto comercial.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo completo se muestra el uso de objetos comerciales en una lista desplegable. En el ejemplo, un control <xref:System.Windows.Forms.DataGridView> se enlaza a una colección de objetos `Task`. Cada `Task` objeto tiene una propiedad `AssignedTo` que indica el objeto `Employee` actualmente asignado a esa tarea. En la columna `Assigned To` se muestra el valor de la propiedad `Name` de cada empleado asignado o "sin asignar" si el valor de la propiedad `Task.AssignedTo` es `null`.  
  
 Para ver el comportamiento de este ejemplo, realice los pasos siguientes:  
  
1. Para cambiar las asignaciones de la columna `Assigned To`, seleccione valores diferentes en las listas desplegables o presione CTRL + 0 en una celda de cuadro combinado.  
  
2. Haga clic en `Generate Report` para mostrar las asignaciones actuales. Esto demuestra que un cambio en la columna `Assigned To` actualiza automáticamente la colección `tasks`.  
  
3. Haga clic en un botón de `Request Status` para llamar al método `RequestStatus` del objeto `Employee` actual de esa fila. Esto demuestra que el objeto seleccionado se ha recuperado correctamente.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System y System.Windows.Forms.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
