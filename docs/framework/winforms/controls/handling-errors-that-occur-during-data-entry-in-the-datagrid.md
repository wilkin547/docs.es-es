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
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046075"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms

La administración de errores del almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos. El control <xref:System.Windows.Forms.DataGridView> Windows Forms facilita esta tarea al exponer el <xref:System.Windows.Forms.DataGridView.DataError> evento, que se genera cuando el almacén de datos detecta una infracción de restricción o una regla de negocios interrumpida.

En este tutorial, recuperará las filas de la `Customers` tabla de la base de datos de ejemplo Northwind y las <xref:System.Windows.Forms.DataGridView> mostrará en un control. Cuando se detecta `CustomerID` un valor duplicado en una fila nueva o en una fila existente modificada, se producirá el <xref:System.Windows.Forms.DataGridView.DataError> evento, que se controlará mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.

Para copiar el código de este tema como una sola lista, vea [Cómo: Controlar los errores que se producen durante la entrada de datos en](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)el control DataGridView Windows Forms.

## <a name="prerequisites"></a>Requisitos previos

Para poder completar este tutorial, necesitará:

- Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.

## <a name="creating-the-form"></a>Crear el formulario

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Para controlar los errores de entrada de datos en el control DataGridView

1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.

    El siguiente ejemplo de código proporciona una inicialización básica `Main` e incluye un método.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.

    En este ejemplo de código `GetData` se usa un método que <xref:System.Data.DataTable> devuelve un objeto rellenado. Asegúrese de establecer la `connectionString` variable en un valor que sea adecuado para la base de datos.

    > [!IMPORTANT]
    > Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que inicializa <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. Controle <xref:System.Windows.Forms.DataGridView.DataError> el evento <xref:System.Windows.Forms.DataGridView>en.

    Si el contexto del error es una operación de confirmación, muestre el error en <xref:System.Windows.Forms.MessageBox>.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>Probar la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Presione F5 para ejecutar la aplicación.

  Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con datos de la tabla customers. Si escribe un valor duplicado para `CustomerID` y confirma la edición, el valor de la celda se revertirá automáticamente y verá un <xref:System.Windows.Forms.MessageBox> mensaje que muestra el error de entrada de datos.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece una descripción básica de las <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y el comportamiento del <xref:System.Windows.Forms.DataGridView> control de varias maneras:

- Cambiar los estilos de borde y encabezado. Para obtener más información, consulte [Cómo Cambiar los estilos de borde y de línea de cuadrícula en](change-the-border-and-gridline-styles-in-the-datagrid.md)el control DataGridView Windows Forms.

- Habilitar o restringir la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control. Para obtener más información, consulte [Cómo Impedir la adición y eliminación de filas en el control](prevent-row-addition-and-deletion-datagridview.md)DataGridView Windows Forms [y cómo: Haga que las columnas sean de solo lectura en el](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.

- Valide la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control. Para obtener más información, vea [Tutorial: Validar datos en el control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control](implementing-virtual-mode-wf-datagridview-control.md)DataGridView Windows Forms.

- Personalizar la apariencia de las celdas. Para obtener más información, vea [Cómo: Personalice la apariencia de las celdas en el control](customize-the-appearance-of-cells-in-the-datagrid.md) DataGridView Windows Forms y [cómo: Establecer estilos de celda predeterminados para el](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedimientos: Controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Tutorial: Validar datos en el control DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
