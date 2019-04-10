---
title: 'Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: 375ac3bd3a178cc059239cf84209ebbf5d6aca11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220583"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms
Con frecuencia es posible que desee mostrar datos tabulares que no proceden de una base de datos. Por ejemplo, desea mostrar el contenido de una matriz bidimensional de cadenas. La <xref:System.Windows.Forms.DataGridView> clase proporciona una manera fácil y altamente personalizable para mostrar datos sin enlace a un origen de datos. En este tutorial se muestra cómo rellenar un <xref:System.Windows.Forms.DataGridView> controlar y administrar la agregación o eliminación de filas en modo "independiente". De forma predeterminada, el usuario puede agregar nuevas filas. Para impedir la adición de la fila, establezca el <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propiedad es `false`.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Crear un Control DataGridView de formularios de Windows independiente](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Para usar un control DataGridView sin enlazar  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene las siguientes declaraciones de variable y `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implemente un `SetupLayout` método de definición de clase del formulario para configurar el diseño del formulario.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Crear un `SetupDataGridView` método para configurar el <xref:System.Windows.Forms.DataGridView> columnas y propiedades.  
  
     Este método se agrega primero el <xref:System.Windows.Forms.DataGridView> control en el formulario <xref:System.Windows.Forms.Control.Controls%2A> colección. A continuación, el número de columnas que se mostrará se establece mediante la <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> propiedad. Se establece el estilo predeterminado para los encabezados de columna estableciendo el <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, y <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> propiedades de la <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por la <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> propiedad.  
  
     Se establecen las propiedades de diseño y la apariencia y, a continuación, se asignan los nombres de columna. Cuando este método finaliza, el <xref:System.Windows.Forms.DataGridView> control está listo para rellenarse.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Crear un `PopulateDataGridView` método para agregar filas a la <xref:System.Windows.Forms.DataGridView> control.  
  
     Cada fila representa una canción y su información asociada.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Con los métodos de utilidad en su lugar, puede adjuntar controladores de eventos.  
  
     Va a controlar el **agregar** y **eliminar** los botones <xref:System.Windows.Forms.Control.Click> eventos, el formulario <xref:System.Windows.Forms.Form.Load> eventos y el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos.  
  
     Cuando el **agregar** del botón <xref:System.Windows.Forms.Control.Click> se provoca el evento, se agrega una fila nueva y vacía el <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando el **eliminar** del botón <xref:System.Windows.Forms.Control.Click> provoca el evento, se elimina la fila seleccionada, a menos que sea la fila para los nuevos registros, que permite al usuario agregar nuevas filas. Esta fila es siempre la última fila de la <xref:System.Windows.Forms.DataGridView> control.  
  
     Cuando el formulario <xref:System.Windows.Forms.Form.Load> se provoca el evento, el `SetupLayout`, `SetupDataGridView`, y `PopulateDataGridView` se denominan métodos de utilidad.  
  
     Cuando el <xref:System.Windows.Forms.DataGridView.CellFormatting> se provoca el evento, cada celda de la `Date` columna tiene el formato como una fecha larga, a menos que el valor de celda no puede analizarse.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> control que muestra las canciones enumeradas en `PopulateDataGridView`. Puede agregar nuevas filas con el **Agregar fila** botón y se pueden eliminar las filas seleccionadas con los **Eliminar fila** botón. El independiente <xref:System.Windows.Forms.DataGridView> control es el almacén de datos y sus datos están independientes de cualquier origen externo, como un <xref:System.Data.DataSet> o una matriz.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le ofrece un conocimiento básico de la <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: Cambiar el borde y los estilos de línea de cuadrícula en la Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), y [Cómo: Crear columnas de sólo lectura en la Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Compruebe la entrada del usuario para errores relacionados con la base de datos. Para obtener más información, vea [Tutorial: Controlar los errores que se producen durante la entrada de datos en la Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Controlar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, vea [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de celda predeterminados para los Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Mostrar datos en el control DataGridView de formularios Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Filtrar para crear un control DataGridView sin enlazar en formularios Windows Forms](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
