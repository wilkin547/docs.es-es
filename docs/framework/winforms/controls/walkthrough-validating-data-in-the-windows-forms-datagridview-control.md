---
title: 'Tutorial: validar datos en el control DataGridView'
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
ms.openlocfilehash: 45753fb206ad58616c9a727bd81bd2458db6053e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740094"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Tutorial: Validar datos en el control DataGridView de formularios Windows Forms

Cuando se muestra la funcionalidad de entrada de datos a los usuarios, a menudo es necesario validar los datos introducidos en el formulario. La clase <xref:System.Windows.Forms.DataGridView> proporciona una manera cómoda de realizar la validación antes de que los datos se confirmen en el almacén de datos. Puede validar los datos controlando el evento <xref:System.Windows.Forms.DataGridView.CellValidating>, generado por el <xref:System.Windows.Forms.DataGridView> cuando cambia la celda actual.

En este tutorial, recuperará filas de la tabla `Customers` en la base de datos de ejemplo Northwind y las mostrará en un control <xref:System.Windows.Forms.DataGridView>. Cuando un usuario edita una celda en la columna de `CompanyName` e intenta salir de la celda, el controlador de eventos de <xref:System.Windows.Forms.DataGridView.CellValidating> examinará la cadena de nombre de empresa nueva para asegurarse de que no esté vacía; Si el nuevo valor es una cadena vacía, el <xref:System.Windows.Forms.DataGridView> impedirá que el cursor del usuario abandone la celda hasta que se especifique una cadena que no esté vacía.

Para copiar el código de este tema como una sola lista, vea [Cómo: validar datos en el control DataGridView Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md).

## <a name="prerequisites"></a>Prerequisites

Para completar esta visita guiada, necesitará:

- Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.

## <a name="creating-the-form"></a>Crear el formulario

#### <a name="to-validate-data-entered-in-a-datagridview"></a>Para validar los datos especificados en DataGridView

1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un control <xref:System.Windows.Forms.DataGridView> y un componente <xref:System.Windows.Forms.BindingSource>.

    El siguiente ejemplo de código proporciona una inicialización básica e incluye un método `Main`.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.

    En este ejemplo de código se usa un método `GetData` que devuelve un objeto <xref:System.Data.DataTable> rellenado. Asegúrese de establecer la variable de `connectionString` en un valor que sea adecuado para la base de datos.

    > [!IMPORTANT]
    > Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows, también conocida como seguridad integrada, es una forma más segura de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Implemente un controlador para el evento de <xref:System.Windows.Forms.Form.Load> del formulario que inicializa el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Implemente Controladores para los eventos <xref:System.Windows.Forms.DataGridView.CellEndEdit> y <xref:System.Windows.Forms.DataGridView.CellValidating> del control de <xref:System.Windows.Forms.DataGridView>.

    El controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValidating> es donde se determina si el valor de una celda de la columna `CompanyName` está vacío. Si el valor de la celda no supera la validación, establezca la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> de la clase <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> en `true`. Esto hace que el control <xref:System.Windows.Forms.DataGridView> impida que el cursor abandone la celda. Establezca la propiedad <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> de la fila en una cadena explicativa. Se muestra un icono de error con una información sobre herramientas que contiene el texto del error. En el controlador de eventos <xref:System.Windows.Forms.DataGridView.CellEndEdit>, establezca la propiedad <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> de la fila en la cadena vacía. El evento <xref:System.Windows.Forms.DataGridView.CellEndEdit> solo se produce cuando la celda sale del modo de edición, lo que no puede hacer si se produce un error en la validación.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Prueba de la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Compile y ejecute la aplicación.

  Verá un <xref:System.Windows.Forms.DataGridView> rellenado con los datos de la tabla `Customers`. Al hacer doble clic en una celda de la columna `CompanyName`, puede editar el valor. Si elimina todos los caracteres y presiona la tecla TAB para salir de la celda, el <xref:System.Windows.Forms.DataGridView> impide salir. Al escribir una cadena no vacía en la celda, el control <xref:System.Windows.Forms.DataGridView> le permite salir de la celda.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece una descripción básica de las capacidades del control de <xref:System.Windows.Forms.DataGridView>. Puede personalizar la apariencia y el comportamiento del control de <xref:System.Windows.Forms.DataGridView> de varias maneras:

- Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: cambiar los estilos de borde y de línea de cuadrícula en el control DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Habilitar o restringir la entrada del usuario al control de <xref:System.Windows.Forms.DataGridView>. Para obtener más información, vea [Cómo: impedir la adición y eliminación de filas en el control datagridview Windows Forms](prevent-row-addition-and-deletion-datagridview.md)y [Cómo: crear columnas de solo lectura en el control DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Compruebe la entrada del usuario para ver si hay errores relacionados con la base de datos. Para obtener más información, vea [Tutorial: controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).

- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).

- Personalizar la apariencia de las celdas. Para obtener más información, vea [Cómo: personalizar la apariencia de las celdas en el control datagridview Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de colores y fuentes en el control DataGridView Windows Forms](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Validar datos en el control DataGridView de formularios Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
