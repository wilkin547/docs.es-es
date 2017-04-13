---
title: "Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
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
  - "DataGridView (control) [Windows Forms], formulario principal/detalle"
  - "listas principal-detalle, mostrar en Windows Forms"
  - "tabla primaria-secundaria, mostrar en Windows Forms"
  - "tutoriales [Windows Forms], DataGridView (control)"
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms
Uno de los escenarios más comunes para utilizar el control <xref:System.Windows.Forms.DataGridView> es el formulario *principal\-detalle*, en el que se muestra una relación primaria\-secundaria entre dos tablas de base de datos.  Al seleccionar filas en la tabla primaria se provoca que la tabla secundaria se actualice con los datos secundarios correspondientes.  
  
 Implementar un formulario principal\/detalle es sencillo con la interacción entre el control <xref:System.Windows.Forms.DataGridView> y el componente <xref:System.Windows.Forms.BindingSource>.  En este tutorial, compilará el formulario mediante dos controles <xref:System.Windows.Forms.DataGridView> y dos componentes <xref:System.Windows.Forms.BindingSource>.  El formulario mostrará dos tablas relacionadas en la base de datos de ejemplo Northwind de SQL Server: `Customers` y `Orders`.  Cuando termine, tendrá un formulario que muestra todos los clientes de la base de datos en el <xref:System.Windows.Forms.DataGridView> principal y todos los pedidos del cliente seleccionado en el <xref:System.Windows.Forms.DataGridView> detalle.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Crear un formulario principal\-detalle mediante dos controles DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor con la base de datos de ejemplo Northwind de SQL Server.  
  
## Crear el formulario  
  
#### Para crear un formulario principal\-detalle  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene dos controles <xref:System.Windows.Forms.DataGridView> y dos componentes <xref:System.Windows.Forms.BindingSource>.  En el ejemplo de código siguiente se proporciona la inicialización básica y se incluye un método `Main`.  Si utiliza el diseñador de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] para crear el formulario, puede utilizar el código generado del diseñador en lugar de este código, pero asegúrese de que utiliza aquí los nombres mostrados en las declaraciones de variable.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de conexión con la base de datos.  Este ejemplo utiliza un método `GetData` que rellena un objeto <xref:System.Data.DataSet>, agrega un objeto <xref:System.Data.DataRelation> al conjunto de datos y enlaza los componentes <xref:System.Windows.Forms.BindingSource>.  Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  El hecho de almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, vea [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que enlaza los controles <xref:System.Windows.Forms.DataGridView> a los componentes <xref:System.Windows.Forms.BindingSource> y llama al método `GetData`.  El ejemplo siguiente incluye código que cambia el tamaño de columnas <xref:System.Windows.Forms.DataGridView> para ajustar los datos mostrados.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá dos controles <xref:System.Windows.Forms.DataGridView>, uno sobre el otro.  En la parte superior están los clientes de la tabla `Customers` de Northwind y en la parte inferior están los `Orders` \(pedidos\) que corresponden al cliente seleccionado.  A medida que selecciona distintas filas en el <xref:System.Windows.Forms.DataGridView> superior, el contenido del <xref:System.Windows.Forms.DataGridView> inferior cambia de modo correspondiente.  
  
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
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Crear un formulario principal\-detalle mediante dos controles DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)