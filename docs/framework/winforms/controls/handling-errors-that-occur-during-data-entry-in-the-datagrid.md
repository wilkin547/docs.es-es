---
title: 'Tutorial: controlar los errores que se producen durante la entrada de datos en el control DataGridView'
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
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738738"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms

La administración de errores del almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos. El control <xref:System.Windows.Forms.DataGridView> de Windows Forms facilita esta tarea al exponer el evento <xref:System.Windows.Forms.DataGridView.DataError>, que se genera cuando el almacén de datos detecta una infracción de restricción o una regla de negocios interrumpida.

En este tutorial, recuperará filas de la tabla `Customers` en la base de datos de ejemplo Northwind y las mostrará en un control <xref:System.Windows.Forms.DataGridView>. Cuando se detecta un valor de `CustomerID` duplicado en una fila nueva o en una fila existente modificada, se producirá el evento <xref:System.Windows.Forms.DataGridView.DataError>, que se controlará mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.

Para copiar el código de este tema como una sola lista, vea [Cómo: controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).

## <a name="prerequisites"></a>Requisitos previos

Para poder completar este tutorial, necesitará:

- Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.

## <a name="creating-the-form"></a>Crear el formulario

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Para controlar los errores de entrada de datos en el control DataGridView

1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un control <xref:System.Windows.Forms.DataGridView> y un componente <xref:System.Windows.Forms.BindingSource>.

    El siguiente ejemplo de código proporciona una inicialización básica e incluye un método `Main`.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.

    En este ejemplo de código se usa un método `GetData` que devuelve un objeto <xref:System.Data.DataTable> rellenado. Asegúrese de establecer la variable de `connectionString` en un valor que sea adecuado para la base de datos.

    > [!IMPORTANT]
    > Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. Implemente un controlador para el evento de <xref:System.Windows.Forms.Form.Load> del formulario que inicializa el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. Controle el evento de <xref:System.Windows.Forms.DataGridView.DataError> en el <xref:System.Windows.Forms.DataGridView>.

    Si el contexto del error es una operación de confirmación, muestra el error en un <xref:System.Windows.Forms.MessageBox>.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>Probar la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Presione F5 para ejecutar la aplicación.

  Verá un control de <xref:System.Windows.Forms.DataGridView> rellenado con los datos de la tabla customers. Si escribe un valor duplicado para `CustomerID` y confirma la edición, el valor de la celda se revertirá automáticamente y verá una <xref:System.Windows.Forms.MessageBox> que muestra el error de entrada de datos.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece una descripción básica de las capacidades del control de <xref:System.Windows.Forms.DataGridView>. Puede personalizar la apariencia y el comportamiento del control de <xref:System.Windows.Forms.DataGridView> de varias maneras:

- Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: cambiar los estilos de borde y de línea de cuadrícula en el control DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Habilitar o restringir la entrada del usuario al control de <xref:System.Windows.Forms.DataGridView>. Para obtener más información, vea [Cómo: impedir la adición y eliminación de filas en el control datagridview Windows Forms](prevent-row-addition-and-deletion-datagridview.md)y [Cómo: crear columnas de solo lectura en el control DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Valide los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>. Para obtener más información, vea [Tutorial: validar datos en el control DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).

- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).

- Personalizar la apariencia de las celdas. Para obtener más información, vea [Cómo: personalizar la apariencia de las celdas en el control datagridview Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de celda predeterminados para el control DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Controlar los errores que se producen durante la entrada de datos en el control DataGridView de Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Tutorial: Validar datos en el control DataGridView de Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
