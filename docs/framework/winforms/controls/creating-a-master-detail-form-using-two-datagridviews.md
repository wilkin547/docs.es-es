---
title: 'Tutorial: crear un formulario principal-detalle mediante dos controles DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: bb3da36430c7493b941f3711cb584b4517d5bd54
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740582"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms

Uno de los escenarios más comunes para usar el control <xref:System.Windows.Forms.DataGridView> es el formulario *principal/detalle* , en el que se muestra una relación de elementos primarios y secundarios entre dos tablas de base de datos. La selección de filas en la tabla maestra hace que la tabla de detalles se actualice con los datos secundarios correspondientes.

La implementación de un formulario principal/detalle es fácil mediante la interacción entre el control <xref:System.Windows.Forms.DataGridView> y el componente <xref:System.Windows.Forms.BindingSource>. En este tutorial, creará el formulario con dos controles <xref:System.Windows.Forms.DataGridView> y dos componentes <xref:System.Windows.Forms.BindingSource>. El formulario mostrará dos tablas relacionadas en la base de datos de ejemplo Northwind SQL Server: `Customers` y `Orders`. Cuando haya terminado, tendrá un formulario que muestra todos los clientes de la base de datos en el <xref:System.Windows.Forms.DataGridView> maestro y todos los pedidos del cliente seleccionado en el <xref:System.Windows.Forms.DataGridView>de detalles.

Para copiar el código de este tema como una sola lista, vea [Cómo: crear un formulario principal-detalle mediante dos controles DataGridView Windows Forms](create-a-master-detail-form-using-two-datagridviews.md).

## <a name="prerequisites"></a>Prerequisites

Para completar esta visita guiada, necesitará:

- Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.

## <a name="creating-the-form"></a>Crear el formulario

#### <a name="to-create-a-masterdetail-form"></a>Para crear un formulario principal/detalle

1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga dos controles <xref:System.Windows.Forms.DataGridView> y dos componentes <xref:System.Windows.Forms.BindingSource>. El código siguiente proporciona una inicialización de formulario básica e incluye un método `Main`. Si usa el diseñador de Visual Studio para crear el formulario, puede usar el código generado por el diseñador en lugar de este código, pero asegúrese de usar los nombres que se muestran en las declaraciones de variable aquí.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos. En este ejemplo se usa un método `GetData` que rellena un objeto <xref:System.Data.DataSet>, agrega un objeto <xref:System.Data.DataRelation> al conjunto de datos y enlaza los componentes <xref:System.Windows.Forms.BindingSource>. Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.

    > [!IMPORTANT]
    > Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Implemente un controlador para el evento de <xref:System.Windows.Forms.Form.Load> del formulario que enlaza los controles <xref:System.Windows.Forms.DataGridView> a los componentes <xref:System.Windows.Forms.BindingSource> y llama al método `GetData`. En el ejemplo siguiente se incluye código que cambia el tamaño de <xref:System.Windows.Forms.DataGridView> columnas para ajustarse a los datos mostrados.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Prueba de la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Compile y ejecute la aplicación.

  Verá dos controles <xref:System.Windows.Forms.DataGridView>, uno sobre el otro. Además, los clientes de la tabla Northwind `Customers` y, en la parte inferior, son los `Orders` correspondientes al cliente seleccionado. A medida que selecciona diferentes filas en el <xref:System.Windows.Forms.DataGridView>superior, el contenido de la <xref:System.Windows.Forms.DataGridView> inferior cambia en consecuencia.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece una descripción básica de las capacidades del control de <xref:System.Windows.Forms.DataGridView>. Puede personalizar la apariencia y el comportamiento del control de <xref:System.Windows.Forms.DataGridView> de varias maneras:

- Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: cambiar los estilos de borde y de línea de cuadrícula en el control DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Habilitar o restringir la entrada del usuario al control de <xref:System.Windows.Forms.DataGridView>. Para obtener más información, vea [Cómo: impedir la adición y eliminación de filas en el control datagridview Windows Forms](prevent-row-addition-and-deletion-datagridview.md)y [Cómo: crear columnas de solo lectura en el control DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Valide los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>. Para obtener más información, vea [Tutorial: validar datos en el control DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).

- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).

- Personalizar la apariencia de las celdas. Para obtener más información, vea [Cómo: personalizar la apariencia de las celdas en el control datagridview Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de celda predeterminados para el control DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
