---
title: 'Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms'
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
ms.openlocfilehash: 92525d1818160f5645b95948910547c7d1541897
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529239"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms
Control de errores desde el almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos. Los formularios Windows Forms <xref:System.Windows.Forms.DataGridView> control facilita esta tarea mediante la exposición de la <xref:System.Windows.Forms.DataGridView.DataError> eventos, que se desencadena cuando el almacén de datos detecta una infracción de restricción o una regla de negocios rota.  
  
 En este tutorial, recuperará filas de la `Customers` de tabla en la base de datos de ejemplo Northwind y mostrarlas en un <xref:System.Windows.Forms.DataGridView> control. Cuando un duplicado `CustomerID` valor se detecta en una nueva fila o una fila existente editada, el <xref:System.Windows.Forms.DataGridView.DataError> se produce un evento que se controlarán mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: controlar los errores que se producen durante la entrada de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Para controlar los errores de entrada de datos en el control DataGridView  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.  
  
     En el ejemplo de código siguiente se proporciona la inicialización básica y se incluye un `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.  
  
     Este ejemplo de código se usa un `GetData` método que devuelva un rellenado <xref:System.Data.DataTable> objeto. Asegúrese de establecer el `connectionString` variable a un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implemente un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializan el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Controlar la <xref:System.Windows.Forms.DataGridView.DataError> evento en el <xref:System.Windows.Forms.DataGridView>.  
  
     Si el contexto para el error es una operación de confirmación, muestre el error en un <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con datos de la tabla Customers. Si escribe un valor duplicado para `CustomerID` y confirmar la edición, el valor de celda se restablecerá automáticamente y aparecerá un <xref:System.Windows.Forms.MessageBox> que muestra el error de entrada de datos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación proporciona una descripción básica de la <xref:System.Windows.Forms.DataGridView> las capacidades del control. Puede personalizar la apariencia y el comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, consulte [Cómo: cambiar el borde y estilos de las líneas de cuadrícula en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada de usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, consulte [Cómo: impedir la adición de fila y eliminación en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), y [Cómo: asegúrese de solo lectura de las columnas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Validar entrada de usuario para el <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, consulte [Tutorial: validar datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Administrar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, consulte [Tutorial: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, consulte [Cómo: personalizar la apariencia de celdas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de celda predeterminados para el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Controlar los errores que se producen durante la entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Tutorial: Validar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
