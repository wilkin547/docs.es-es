---
title: "Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "entrada de datos, control de errores"
  - "cuadrículas de datos, control de errores"
  - "DataGridView (control) [Windows Forms], control de errores"
  - "control de errores, entrada de datos"
  - "control de errores, DataGridView (control)"
  - "tutoriales [Windows Forms], DataGridView (control)"
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms
Una característica necesaria para una aplicación de entrada de datos es el control de errores del almacén de datos subyacente.  El control <xref:System.Windows.Forms.DataGridView> de formularios Windows Forms facilita ésto exponiendo el evento <xref:System.Windows.Forms.DataGridView.DataError>, que se produce cuando el almacén de datos detecta una infracción de restricción o de regla empresarial.  
  
 En este tutorial, recuperará filas de la tabla `Customers` de la base de datos de ejemplo Northwind y las mostrará en un control <xref:System.Windows.Forms.DataGridView>.  Si se detecta un valor de `CustomerID` duplicado en una nueva fila o una fila existente editada, se producirá el evento <xref:System.Windows.Forms.DataGridView.DataError>, que se puede controlar mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor con la base de datos de ejemplo Northwind de SQL Server.  
  
## Crear el formulario  
  
#### Para controlar los errores de entrada de datos del control DataGridView  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un control <xref:System.Windows.Forms.DataGridView> y un componente <xref:System.Windows.Forms.BindingSource>.  
  
     En el ejemplo de código siguiente se proporciona la inicialización básica y se incluye un método `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de conexión con la base de datos.  
  
     En este ejemplo de código se utiliza un método  `GetData`  que devuelve un objeto <xref:System.Data.DataTable> rellenado.  Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  El hecho de almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, vea [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que inicializa <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Controle el evento <xref:System.Windows.Forms.DataGridView.DataError> en <xref:System.Windows.Forms.DataGridView>.  
  
     Si el contexto del error es una operación de confirmación, muestre el error en <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Aparecerá un control <xref:System.Windows.Forms.DataGridView> rellenado con datos de la tabla Customers.  Si especifica un valor duplicado para `CustomerID` y confirma la edición, se invertirá automáticamente el valor de la celda y aparecerá un <xref:System.Windows.Forms.MessageBox> que muestra el error de la entrada de datos.  
  
## Pasos siguientes  
 Esta aplicación proporciona conocimientos básicos sobre las funciones del control <xref:System.Windows.Forms.DataGridView>.  Puede personalizar la apariencia y el comportamiento del control <xref:System.Windows.Forms.DataGridView> de varias formas:  
  
-   Cambie los estilos de borde y encabezado.  Para obtener más información, vea [Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Permita o restringa los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>.  Para obtener más información, vea [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) y [Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Valide los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>.  Para obtener más información, vea [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Controle conjuntos de grandes volúmenes de datos utilizando el modo virtual.  Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalice la apariencia de las celdas.  Para obtener más información, vea [Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)