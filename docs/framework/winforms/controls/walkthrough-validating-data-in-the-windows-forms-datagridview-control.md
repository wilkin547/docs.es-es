---
title: 'Tutorial: Validar datos en el control DataGridView de formularios Windows Forms'
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
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b460afb393c1b88b34281a8db1b61203e5c5962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Tutorial: Validar datos en el control DataGridView de formularios Windows Forms
Cuando se muestra la funcionalidad de entrada de datos a los usuarios, suelen incluir que validar los datos introducidos en el formulario. La <xref:System.Windows.Forms.DataGridView> clase proporciona una manera cómoda de realizar la validación antes de datos se confirma en el almacén de datos. Puede validar los datos controlando el <xref:System.Windows.Forms.DataGridView.CellValidating> evento, que se genera mediante el <xref:System.Windows.Forms.DataGridView> cuando cambia la celda actual.  
  
 En este tutorial, recuperará filas de la `Customers` de tabla en la base de datos de ejemplo Northwind y mostrarlas en un <xref:System.Windows.Forms.DataGridView> control. Cuando un usuario edita una celda en el `CompanyName` columna e intenta abandonar la celda, el <xref:System.Windows.Forms.DataGridView.CellValidating> controlador de eventos examinará la nueva cadena de nombre de empresa para asegurarse de que es no está vacío; si el nuevo valor es una cadena vacía, el <xref:System.Windows.Forms.DataGridView> impedirá que el cursor del usuario abandone la celda hasta que se especifique una cadena no vacía.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: validar datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>Validar datos introducidos en un control DataGridView  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.  
  
     En el ejemplo de código siguiente se proporciona la inicialización básica y se incluye un `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.  
  
     Este ejemplo de código se usa un `GetData` método que devuelva un rellenado <xref:System.Data.DataTable> objeto. Asegúrese de establecer el `connectionString` variable a un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. Mediante la autenticación de Windows, también conocida como seguridad integrada, es una forma más segura de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implemente un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializan el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implemente los controladores para la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellValidating> y <xref:System.Windows.Forms.DataGridView.CellEndEdit> eventos.  
  
     El <xref:System.Windows.Forms.DataGridView.CellValidating> controlador de eventos es donde se determina si el valor de una celda en la `CompanyName` columna está vacía. Si el valor de celda no supera la validación, establezca la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> clase a `true`. Esto hace que el <xref:System.Windows.Forms.DataGridView> control para evitar que el cursor abandone la celda. Establecer el <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> propiedad en la fila en una cadena explicativa. Esto muestra un icono de error con información sobre herramientas que contiene el texto del error. En el <xref:System.Windows.Forms.DataGridView.CellEndEdit> controlador de eventos, establezca la <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> propiedad en la fila en la cadena vacía. El <xref:System.Windows.Forms.DataGridView.CellEndEdit> evento produce solo cuando la celda sale del modo de edición, lo no puede realizar si se produce un error de validación.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> rellenado con datos de la `Customers` tabla. Al hacer doble clic en una celda de la `CompanyName` columna, se puede editar el valor. Si elimina todos los caracteres y presionar la tecla TAB para salir de la celda, el <xref:System.Windows.Forms.DataGridView> impide que salga. Cuando se escribe una cadena no vacía en la celda, el <xref:System.Windows.Forms.DataGridView> control le permite salir de la celda.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación proporciona una descripción básica de la <xref:System.Windows.Forms.DataGridView> las capacidades del control. Puede personalizar la apariencia y el comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, consulte [Cómo: cambiar el borde y estilos de las líneas de cuadrícula en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada de usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, consulte [Cómo: impedir la adición de fila y eliminación en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), y [Cómo: asegúrese de solo lectura de las columnas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Compruebe la entrada del usuario para errores relacionados con la base de datos. Para obtener más información, consulte [Tutorial: controlar los errores que se producen durante la entrada de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Administrar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, consulte [Tutorial: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, consulte [Cómo: personalizar la apariencia de celdas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer fuentes y estilos de colores en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)  
 [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
