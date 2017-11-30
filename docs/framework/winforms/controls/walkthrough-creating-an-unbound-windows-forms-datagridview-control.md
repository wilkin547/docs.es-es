---
title: 'Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2c57cfbab4d3af6cebff96517383999ae5b73d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms
Con frecuencia puede mostrar datos tabulares que no proceden de una base de datos. Por ejemplo, puede mostrar el contenido de una matriz bidimensional de cadenas. La <xref:System.Windows.Forms.DataGridView> clase proporciona una manera fácil y muy personalizable para mostrar datos sin enlace a un origen de datos. Este tutorial muestra cómo rellenar un <xref:System.Windows.Forms.DataGridView> controlar y administrar la adición y eliminación de filas en modo "independiente". De forma predeterminada, el usuario puede agregar nuevas filas. Para impedir la adición de fila, establezca la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propiedad es `false`.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: crear un DataGridView Control de Windows Forms sin enlazar](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Para usar un control DataGridView sin enlazar  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene las siguientes declaraciones de variable y `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implemente un `SetupLayout` método en la definición de clase del formulario para configurar el diseño del formulario.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Crear un `SetupDataGridView` método para configurar la <xref:System.Windows.Forms.DataGridView> columnas y propiedades.  
  
     Este método primero agrega el <xref:System.Windows.Forms.DataGridView> control en el formulario <xref:System.Windows.Forms.Control.Controls%2A> colección. A continuación, se establece el número de columnas que se mostrará mediante el <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> propiedad. Se establece el estilo predeterminado para los encabezados de columna estableciendo el <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, y <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> propiedades de la <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por la <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> propiedad.  
  
     Se establecen las propiedades de diseño y la apariencia y, a continuación, se asignan los nombres de columna. Cuando este método finaliza, el <xref:System.Windows.Forms.DataGridView> control está listo para rellenarla.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Crear un `PopulateDataGridView` método para agregar filas a la <xref:System.Windows.Forms.DataGridView> control.  
  
     Cada fila representa una canción y su información asociada.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Con los métodos de utilidad en su lugar, puede adjuntar controladores de eventos.  
  
     Va a controlar la **agregar** y **eliminar** botones <xref:System.Windows.Forms.Control.Click> eventos, el formulario <xref:System.Windows.Forms.Form.Load> eventos y el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos.  
  
     Cuando el **agregar** del botón <xref:System.Windows.Forms.Control.Click> evento se desencadena, se agrega una fila nueva y vacía a la <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando el **eliminar** del botón <xref:System.Windows.Forms.Control.Click> evento se desencadena, se elimina la fila seleccionada, a menos que sea la fila para nuevos registros, que permite al usuario agregar nuevas filas. Esta fila siempre es la última fila en la <xref:System.Windows.Forms.DataGridView> control.  
  
     Cuando el formulario <xref:System.Windows.Forms.Form.Load> evento se desencadena, el `SetupLayout`, `SetupDataGridView`, y `PopulateDataGridView` se llaman a métodos de utilidad.  
  
     Cuando el <xref:System.Windows.Forms.DataGridView.CellFormatting> evento se desencadena, cada celda de la `Date` columna tiene el formato como una fecha larga, a menos que no se puede analizar el valor de la celda.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> control que muestra las canciones enumeradas en `PopulateDataGridView`. Puede agregar nuevas filas con el **Agregar fila** botón y se pueden eliminar las filas seleccionadas con los **Eliminar fila** botón. El independiente <xref:System.Windows.Forms.DataGridView> control es el almacén de datos y sus datos están independientes de cualquier origen externo, como un <xref:System.Data.DataSet> o una matriz.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación proporciona una descripción básica de la <xref:System.Windows.Forms.DataGridView> las capacidades del control. Puede personalizar la apariencia y el comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, consulte [Cómo: cambiar el borde y estilos de las líneas de cuadrícula en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada de usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, consulte [Cómo: impedir la adición de fila y eliminación en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), y [Cómo: asegúrese de solo lectura de las columnas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Compruebe la entrada del usuario para errores relacionados con la base de datos. Para obtener más información, consulte [Tutorial: controlar los errores que se producen durante la entrada de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Administrar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, consulte [Tutorial: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, consulte [Cómo: personalizar la apariencia de celdas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de celda predeterminados para el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Crear un control DataGridView no enlazado en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)  
 [Modos de presentación de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
