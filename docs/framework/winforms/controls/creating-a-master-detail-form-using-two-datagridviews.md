---
title: 'Tutorial: Crear un formulario principal-detalle mediante dos controles Windows Forms DataGridView'
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
ms.openlocfilehash: 4212c7223aca6a5e7de3189d5f6b2757453cc438
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046095"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Tutorial: Crear un formulario maestro y detalle mediante dos controles DataGridView de formularios Windows Forms

Uno de los escenarios más comunes para usar el <xref:System.Windows.Forms.DataGridView> control es el formulario *principal/detalle* , en el que se muestra una relación de elementos primarios y secundarios entre dos tablas de base de datos. La selección de filas en la tabla maestra hace que la tabla de detalles se actualice con los datos secundarios correspondientes.

Implementar un formulario principal/detalle es fácil usando la interacción entre el <xref:System.Windows.Forms.DataGridView> control y el <xref:System.Windows.Forms.BindingSource> componente. En este tutorial, creará el formulario con dos <xref:System.Windows.Forms.DataGridView> controles y dos <xref:System.Windows.Forms.BindingSource> componentes. El formulario mostrará dos tablas relacionadas en la base de datos de ejemplo Northwind `Customers` SQL Server `Orders`: y. Cuando haya terminado, tendrá un formulario que muestra todos los clientes de la base de datos del maestro <xref:System.Windows.Forms.DataGridView> y todos los pedidos del cliente seleccionado en el detalle. <xref:System.Windows.Forms.DataGridView>

Para copiar el código de este tema como una sola lista, vea [Cómo: Cree un formulario principal-detalle mediante dos controles](create-a-master-detail-form-using-two-datagridviews.md)DataGridView Windows Forms.

## <a name="prerequisites"></a>Requisitos previos

Para poder completar este tutorial, necesitará:

- Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.

## <a name="creating-the-form"></a>Crear el formulario

#### <a name="to-create-a-masterdetail-form"></a>Para crear un formulario principal/detalle

1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga dos <xref:System.Windows.Forms.DataGridView> controles y dos <xref:System.Windows.Forms.BindingSource> componentes. El código siguiente proporciona una inicialización de formulario básica `Main` e incluye un método. Si usa el diseñador de Visual Studio para crear el formulario, puede usar el código generado por el diseñador en lugar de este código, pero asegúrese de usar los nombres que se muestran en las declaraciones de variable aquí.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos. En este ejemplo se `GetData` utiliza un método que rellena <xref:System.Data.DataSet> un objeto, agrega <xref:System.Data.DataRelation> un objeto al conjunto de datos y enlaza los <xref:System.Windows.Forms.BindingSource> componentes. Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.

    > [!IMPORTANT]
    > Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> de su formulario que enlaza <xref:System.Windows.Forms.DataGridView> los controles a <xref:System.Windows.Forms.BindingSource> los componentes y llama `GetData` al método. En el ejemplo siguiente se incluye código que cambia <xref:System.Windows.Forms.DataGridView> el tamaño de las columnas para ajustarse a los datos mostrados.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Probar la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Compile y ejecute la aplicación.

  Verá dos <xref:System.Windows.Forms.DataGridView> controles, uno sobre el otro. En primer lugar, los clientes de la `Customers` tabla Northwind y en la parte inferior son `Orders` los correspondientes al cliente seleccionado. A medida que selecciona diferentes filas en la <xref:System.Windows.Forms.DataGridView>parte superior, el contenido del <xref:System.Windows.Forms.DataGridView> cambio inferior en consecuencia.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece una descripción básica de las <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y el comportamiento del <xref:System.Windows.Forms.DataGridView> control de varias maneras:

- Cambiar los estilos de borde y encabezado. Para obtener más información, consulte [Cómo Cambiar los estilos de borde y de línea de cuadrícula en](change-the-border-and-gridline-styles-in-the-datagrid.md)el control DataGridView Windows Forms.

- Habilitar o restringir la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control. Para obtener más información, vea [Cómo: Impedir la adición y eliminación de filas en el control](prevent-row-addition-and-deletion-datagridview.md)DataGridView Windows Forms [y cómo: Haga que las columnas sean de solo lectura en el](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.

- Valide la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control. Para obtener más información, vea [Tutorial: Validar datos en el control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control](implementing-virtual-mode-wf-datagridview-control.md)DataGridView Windows Forms.

- Personalizar la apariencia de las celdas. Para obtener más información, consulte [Cómo Personalice la apariencia de las celdas en el control](customize-the-appearance-of-cells-in-the-datagrid.md) DataGridView Windows Forms y [cómo: Establecer estilos de celda predeterminados para el](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Crear un formulario principal-detalle mediante dos controles DataGridView Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
