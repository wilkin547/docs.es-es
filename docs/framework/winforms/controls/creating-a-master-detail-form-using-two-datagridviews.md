---
title: 'Tutorial: Creación de un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms'
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
ms.openlocfilehash: 66807287dcaffae4bd310040312e0f56e8fda5d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078882"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Tutorial: Crear un formulario maestro y detalle mediante dos controles DataGridView de formularios Windows Forms
Uno de los escenarios más comunes para usar el <xref:System.Windows.Forms.DataGridView> control es el *principal-detalle* formulario, en el que se muestra una relación primaria-secundaria entre dos tablas de base de datos. Selección de filas en la tabla maestra hace que la tabla de detalles actualizar con los datos secundarios correspondientes.  
  
 Implementar un formulario principal-detalle es fácil con la interacción entre el <xref:System.Windows.Forms.DataGridView> control y el <xref:System.Windows.Forms.BindingSource> componente. En este tutorial, compilará el formulario mediante dos <xref:System.Windows.Forms.DataGridView> controles y dos <xref:System.Windows.Forms.BindingSource> componentes. El formulario mostrará dos tablas relacionadas en la base de datos de ejemplo Northwind de SQL Server: `Customers` y `Orders`. Cuando haya terminado, tendrá un formulario que muestra todos los clientes de la base de datos en el servidor maestro <xref:System.Windows.Forms.DataGridView> y todos los pedidos del cliente seleccionado en el detalle <xref:System.Windows.Forms.DataGridView>.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms](create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-create-a-masterdetail-form"></a>Para crear un formulario principal-detalle  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene dos <xref:System.Windows.Forms.DataGridView> controles y dos <xref:System.Windows.Forms.BindingSource> componentes. El código siguiente proporciona la inicialización de un formulario básico e incluye un `Main` método. Si usa el Diseñador de Visual Studio para crear el formulario, puede usar el código generado del diseñador en lugar de este código, pero asegúrese de usar los nombres que aparecen en las declaraciones de variable.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos. Este ejemplo se usa un `GetData` método que rellena un <xref:System.Data.DataSet> de objetos, se agrega un <xref:System.Data.DataRelation> objeto para el conjunto de datos y se enlaza el <xref:System.Windows.Forms.BindingSource> componentes. Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que enlaza la <xref:System.Windows.Forms.DataGridView> controles a la <xref:System.Windows.Forms.BindingSource> componentes y llama a la `GetData` método. En el ejemplo siguiente se incluye código que cambia el tamaño de <xref:System.Windows.Forms.DataGridView> columnas para que quepan los datos mostrados.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá dos <xref:System.Windows.Forms.DataGridView> controla uno encima del otro. En la parte superior son los clientes de Northwind `Customers` de tabla y, en la parte inferior está la `Orders` correspondiente al cliente seleccionado. Seleccionar filas diferentes en la esquina superior <xref:System.Windows.Forms.DataGridView>, el contenido de la parte inferior <xref:System.Windows.Forms.DataGridView> cambia en consecuencia.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le ofrece un conocimiento básico de la <xref:System.Windows.Forms.DataGridView> capacidades del control. Puede personalizar la apariencia y comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:  
  
-   Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: Cambiar el borde y los estilos de línea de cuadrícula en la Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Habilitar o restringir la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), y [Cómo: Crear columnas de sólo lectura en la Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Validar la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [Tutorial: Validar datos en el Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Controlar grandes conjuntos de datos utilizando el modo virtual. Para obtener más información, vea [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizar la apariencia de celdas. Para obtener más información, vea [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de celda predeterminados para los Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Mostrar datos en el control DataGridView de formularios Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Filtrar para crear un formulario maestro y detalle mediante dos controles DataGridView de formularios Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
