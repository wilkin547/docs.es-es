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
ms.openlocfilehash: 89569feb0cb741f56d09f4e58154b4eecb5a89d4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046378"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Tutorial: Validar datos en el control DataGridView de formularios Windows Forms

Cuando se muestra la funcionalidad de entrada de datos a los usuarios, a menudo es necesario validar los datos introducidos en el formulario. La <xref:System.Windows.Forms.DataGridView> clase proporciona una manera cómoda de realizar la validación antes de que los datos se confirmen en el almacén de datos. Puede validar los datos controlando el <xref:System.Windows.Forms.DataGridView.CellValidating> evento, que genera <xref:System.Windows.Forms.DataGridView> cuando cambia la celda actual.

En este tutorial, recuperará las filas de la `Customers` tabla de la base de datos de ejemplo Northwind y las <xref:System.Windows.Forms.DataGridView> mostrará en un control. Cuando un usuario edita una celda de la columna `CompanyName` e intenta salir de la celda, el controlador <xref:System.Windows.Forms.DataGridView.CellValidating> de eventos examinará la cadena del nombre de la compañía nueva para asegurarse de que no está vacía; si el nuevo valor es una <xref:System.Windows.Forms.DataGridView> cadena vacía, el evitará el cursor del usuario dejar la celda hasta que se escriba una cadena que no esté vacía.

Para copiar el código de este tema como una sola lista, vea [Cómo: Validar datos en el control](how-to-validate-data-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

## <a name="prerequisites"></a>Requisitos previos

Para poder completar este tutorial, necesitará:

- Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.

## <a name="creating-the-form"></a>Crear el formulario

#### <a name="to-validate-data-entered-in-a-datagridview"></a>Para validar los datos especificados en DataGridView

1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.

    El siguiente ejemplo de código proporciona una inicialización básica `Main` e incluye un método.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.

    En este ejemplo de código `GetData` se usa un método que <xref:System.Data.DataTable> devuelve un objeto rellenado. Asegúrese de establecer la `connectionString` variable en un valor que sea adecuado para la base de datos.

    > [!IMPORTANT]
    > Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows, también conocida como seguridad integrada, es una forma más segura de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que inicializa <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Implemente Controladores para los <xref:System.Windows.Forms.DataGridView> eventos y <xref:System.Windows.Forms.DataGridView.CellValidating> <xref:System.Windows.Forms.DataGridView.CellEndEdit> del control.

    El <xref:System.Windows.Forms.DataGridView.CellValidating> controlador de eventos es donde se determina si el valor de una celda de `CompanyName` la columna está vacío. Si el valor de la celda no supera la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> validación, establezca <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> la propiedad `true`de la clase en. Esto hace que <xref:System.Windows.Forms.DataGridView> el control Evite que el cursor abandone la celda. Establezca la <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> propiedad de la fila en una cadena explicativa. Se muestra un icono de error con una información sobre herramientas que contiene el texto del error. En el controlador de <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> eventos,establezcalapropiedaddelafilaenunacadenavacía.<xref:System.Windows.Forms.DataGridView.CellEndEdit> El <xref:System.Windows.Forms.DataGridView.CellEndEdit> evento solo se produce cuando la celda sale del modo de edición, lo que no puede hacer si se produce un error en la validación.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Probar la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Compile y ejecute la aplicación.

  Verá un <xref:System.Windows.Forms.DataGridView> rellenado con datos de la `Customers` tabla. Al hacer doble clic en una celda de la `CompanyName` columna, puede editar el valor. Si elimina todos los caracteres y presiona la tecla TAB para salir de la celda, <xref:System.Windows.Forms.DataGridView> impide salir. Al escribir una cadena no vacía en la celda, el <xref:System.Windows.Forms.DataGridView> control le permite salir de la celda.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece una descripción básica de las <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y el comportamiento del <xref:System.Windows.Forms.DataGridView> control de varias maneras:

- Cambiar los estilos de borde y encabezado. Para obtener más información, consulte [Cómo Cambiar los estilos de borde y de línea de cuadrícula en](change-the-border-and-gridline-styles-in-the-datagrid.md)el control DataGridView Windows Forms.

- Habilitar o restringir la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control. Para obtener más información, vea [Cómo: Impedir la adición y eliminación de filas en el control](prevent-row-addition-and-deletion-datagridview.md)DataGridView Windows Forms [y cómo: Haga que las columnas sean de solo lectura en el](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.

- Compruebe la entrada del usuario para ver si hay errores relacionados con la base de datos. Para obtener más información, vea [Tutorial: Controlar los errores que se producen durante la entrada de datos en](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)el control DataGridView Windows Forms.

- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control](implementing-virtual-mode-wf-datagridview-control.md)DataGridView Windows Forms.

- Personalizar la apariencia de las celdas. Para obtener más información, consulte [Cómo Personalice la apariencia de las celdas en el control](customize-the-appearance-of-cells-in-the-datagrid.md) DataGridView Windows Forms y [cómo: Establezca los estilos de fuente y color en el control](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Cómo: Validar datos en el control DataGridView Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
