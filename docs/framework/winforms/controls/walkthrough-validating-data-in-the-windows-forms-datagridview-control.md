---
title: 'Tutorial: Validar datos en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: a4bf0850b28b7101ba76f1c1fedc6633eccb81a1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346059"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Tutorial: Validar datos en el control DataGridView de formularios Windows Forms
Cuando se muestra la funcionalidad de entrada de datos a los usuarios, con frecuencia tendrá que validar los datos escritos en el formulario. La <xref:System.Windows.Forms.DataGridView> clase proporciona una manera cómoda para realizar la validación antes de datos se confirma en el almacén de datos. Puede validar los datos controlando el <xref:System.Windows.Forms.DataGridView.CellValidating> evento, que genera el <xref:System.Windows.Forms.DataGridView> cuando cambia la celda actual.  
  
 En este tutorial, va a recuperar las filas de la `Customers` de tabla en la base de datos de ejemplo Northwind y mostrarlos en un <xref:System.Windows.Forms.DataGridView> control. Cuando un usuario edita una celda en la `CompanyName` columna e intenta abandonar la celda, el <xref:System.Windows.Forms.DataGridView.CellValidating> controlador de eventos examinará la nueva cadena de nombre de empresa para asegurarse de que es no está vacío; si el nuevo valor es una cadena vacía, el <xref:System.Windows.Forms.DataGridView> impedirá que el cursor del usuario abandone la celda hasta que se especifique una cadena no vacía.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Validar datos en el Control DataGridView de formularios de Windows](how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>Para validar datos introducidos en un control DataGridView  
  
1. Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.  
  
     En el ejemplo de código siguiente se proporciona la inicialización básica e incluye un `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.  
  
     Este ejemplo de código se usa un `GetData` método que devuelva un rellenado <xref:System.Data.DataTable> objeto. Asegúrese de establecer el `connectionString` variable en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. Mediante la autenticación de Windows, también conocida como seguridad integrada, es una forma más segura de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3. Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializa el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4. Implementar controladores para la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellValidating> y <xref:System.Windows.Forms.DataGridView.CellEndEdit> eventos.  
  
     El <xref:System.Windows.Forms.DataGridView.CellValidating> controlador de eventos es donde se determina si el valor de una celda de la `CompanyName` columna está vacía. Si el valor de celda se produce un error de validación, establezca la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> clase `true`. Esto hace que el <xref:System.Windows.Forms.DataGridView> control para evitar que el cursor abandone la celda. Establecer el <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> propiedad en la fila en una cadena explicativa. Esto muestra un icono de error con información sobre herramientas que contiene el texto del error. En el <xref:System.Windows.Forms.DataGridView.CellEndEdit> controlador de eventos, establezca la <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> propiedad en la fila en la cadena vacía. El <xref:System.Windows.Forms.DataGridView.CellEndEdit> evento produce sólo cuando la celda sale del modo de edición, lo no se puede hacer si se produce un error de validación.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> rellenado con datos de la `Customers` tabla. Cuando haga doble clic en una celda de la `CompanyName` columna, puede editar el valor. Si elimina todos los caracteres y presionar la tecla TAB para salir de la celda, el <xref:System.Windows.Forms.DataGridView> impide que salga. Cuando se escribe una cadena no vacía en la celda, el <xref:System.Windows.Forms.DataGridView> control le permite salir de la celda.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le ofrece un conocimiento básico de la <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: Cambiar el borde y los estilos de línea de cuadrícula en la Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), y [Cómo: Crear columnas de sólo lectura en la Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Compruebe la entrada del usuario para errores relacionados con la base de datos. Para obtener más información, vea [Tutorial: Controlar los errores que se producen durante la entrada de datos en la Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Controlar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, vea [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de colores y fuentes en el Control DataGridView de Windows Forms](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Entrada de datos en el control DataGridView de formularios Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Filtrar para validar datos en el control DataGridView de formularios Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
