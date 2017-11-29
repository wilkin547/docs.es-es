---
title: 'Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de Windows Forms'
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
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d213d70d6f12cb8b574f07457c1b20317670d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms
Uno de los escenarios más comunes para usar el <xref:System.Windows.Forms.DataGridView> control es el *principal-detalle* formulario, en el que se muestra una relación primaria-secundaria entre dos tablas de base de datos. Selección de filas en la tabla maestra hace que la tabla de detalles se actualiza con los datos secundarios correspondientes.  
  
 Implementar un formulario principal-detalle es fácil con la interacción entre el <xref:System.Windows.Forms.DataGridView> control y la <xref:System.Windows.Forms.BindingSource> componente. En este tutorial, creará el formulario mediante dos <xref:System.Windows.Forms.DataGridView> controles y dos <xref:System.Windows.Forms.BindingSource> componentes. El formulario mostrará dos tablas relacionadas en la base de datos de ejemplo Northwind de SQL Server: `Customers` y `Orders`. Cuando haya terminado, tendrá un formulario que muestra todos los clientes en la base de datos en el maestro de <xref:System.Windows.Forms.DataGridView> y todos los pedidos del cliente seleccionado en el detalle <xref:System.Windows.Forms.DataGridView>.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: crear un principal-detalle formulario usando dos controles Windows Forms DataGridView](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-create-a-masterdetail-form"></a>Para crear un formulario principal-detalle  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene dos <xref:System.Windows.Forms.DataGridView> controles y dos <xref:System.Windows.Forms.BindingSource> componentes. El código siguiente proporciona la inicialización de forma básica e incluye un `Main` método. Si usas el [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] diseñador para crear el formulario, puede utilizar el código generado del diseñador en lugar de este código, pero asegúrese de usar los nombres mostrados en las declaraciones de variable.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos. Este ejemplo se utiliza un `GetData` método que rellena un <xref:System.Data.DataSet> de objetos, agrega un <xref:System.Data.DataRelation> objeto para el conjunto de datos y enlaza la <xref:System.Windows.Forms.BindingSource> componentes. Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> evento que enlaza el <xref:System.Windows.Forms.DataGridView> controles a la <xref:System.Windows.Forms.BindingSource> componentes y llama el `GetData` método. En el ejemplo siguiente se incluye código que cambia el tamaño de <xref:System.Windows.Forms.DataGridView> columnas para que quepan los datos mostrados.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá dos <xref:System.Windows.Forms.DataGridView> controla, uno encima de otro. En la parte superior están los clientes de Northwind `Customers` de tabla y en la parte inferior está la `Orders` correspondiente para el cliente seleccionado. Seleccionar los diferentes filas en la esquina superior <xref:System.Windows.Forms.DataGridView>, el contenido de la parte inferior <xref:System.Windows.Forms.DataGridView> cambian en consecuencia.  
  
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
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
