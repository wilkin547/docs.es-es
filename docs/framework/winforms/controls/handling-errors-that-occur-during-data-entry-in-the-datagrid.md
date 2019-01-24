---
title: 'Tutorial: Controlar los errores que se producen durante la entrada de datos en el Control DataGridView de Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: b47185118441b60302ef8c8dc8418f7c6a873e2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644838"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Tutorial: Controlar los errores que se producen durante la entrada de datos en el Control DataGridView de Windows Forms
Control de errores del almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos. Los formularios de Windows <xref:System.Windows.Forms.DataGridView> control facilita esta tarea mediante la exposición de la <xref:System.Windows.Forms.DataGridView.DataError> evento, que se produce cuando el almacén de datos detecta una infracción de restricción o una regla de negocios roto.  
  
 En este tutorial, va a recuperar las filas de la `Customers` de tabla en la base de datos de ejemplo Northwind y mostrarlos en un <xref:System.Windows.Forms.DataGridView> control. Cuando un duplicado `CustomerID` se detecta el valor en una nueva fila o una fila existente editada, el <xref:System.Windows.Forms.DataGridView.DataError> se produce un evento que se controlarán mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Controlar los errores que se producen durante la entrada de datos en la Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Para controlar los errores de entrada de datos en el control DataGridView  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.  
  
     En el ejemplo de código siguiente se proporciona la inicialización básica e incluye un `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.  
  
     Este ejemplo de código se usa un `GetData` método que devuelva un rellenado <xref:System.Data.DataTable> objeto. Asegúrese de establecer el `connectionString` variable en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializa el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Controlar la <xref:System.Windows.Forms.DataGridView.DataError> eventos en el <xref:System.Windows.Forms.DataGridView>.  
  
     Si el contexto del error es una operación de confirmación, se mostrará el error en un <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con datos de la tabla Customers. Si escribe un valor duplicado para `CustomerID` y confirmar la edición, el valor de celda se restablecerá automáticamente y aparecerá un <xref:System.Windows.Forms.MessageBox> que muestra el error de entrada de datos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le ofrece un conocimiento básico de la <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: Cambiar el borde y los estilos de línea de cuadrícula en la Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), y [Cómo: Crear columnas de sólo lectura en la Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Validar la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [Tutorial: Validar datos en el Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Controlar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, vea [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de celda predeterminados para los Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [Cómo: Controlar los errores que se producen durante la entrada de datos en el Control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Tutorial: Validar datos en el Control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
