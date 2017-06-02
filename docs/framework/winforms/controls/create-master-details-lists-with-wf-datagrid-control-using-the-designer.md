---
title: "C&#243;mo: Crear listas Principal-Detalle con el control DataGrid de Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "DataGrid (control) [Windows Forms], listas principal-detalle"
  - "listas principal-detalle"
  - "tablas relacionadas, mostrar en un control DataGrid"
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear listas Principal-Detalle con el control DataGrid de Windows Forms mediante el Dise&#241;ador
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Si un objeto <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos controles <xref:System.Windows.Forms.DataGrid> para mostrar los datos en formato principal\-detalle.  De este modo, un control <xref:System.Windows.Forms.DataGrid> se designa como cuadrícula principal y el otro como cuadrícula de detalles.  Al seleccionar una entrada en la lista principal, la lista de detalles muestra todas las entradas secundarias relacionadas.  Por ejemplo, si el objeto <xref:System.Data.DataSet> contiene una tabla Customers y una tabla relacionada Orders, se especificaría la tabla Customers como cuadrícula principal y la tabla Orders como cuadrícula de detalles.  Al seleccionar un cliente en la cuadrícula principal, la cuadrícula de detalles mostraría todos los pedidos asociados con ese cliente en la tabla Orders.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows**.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear una lista principal\-detalle en el diseñador  
  
1.  Agregue dos controles <xref:System.Windows.Forms.DataGrid> al formulario.  Para obtener más información, vea [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], el control <xref:System.Windows.Forms.DataGrid> no está en el **Cuadro de herramientas** de manera predeterminada.  Para obtener más información, vea [How to: Add Items to the Toolbox](http://msdn.microsoft.com/es-es/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Los pasos siguientes no son aplicables a [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], que utiliza la ventana **Orígenes de datos** para el enlace de datos en tiempo de diseño.  Para obtener más información, vea [Enlazar controles a los datos en Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md) y [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md).  
  
2.  Arrastre al formulario dos o más tablas desde el **Explorador de servidores**.  
  
3.  En el menú **Datos**, seleccione **Generar conjunto de datos**.  
  
4.  Establezca las relaciones entre las tablas por medio del Diseñador XML.  Para obtener información detallada, vea "How to: Create One\-to\-Many Relationships in XML Schemas and Datasets" en MSDN.  
  
5.  Guarde la relación seleccionando **Guardar todo** en el menú **Archivo**.  
  
6.  Configure el control <xref:System.Windows.Forms.DataGrid> que desee designar como cuadrícula principal, como se detalla a continuación:  
  
    1.  Seleccione el objeto <xref:System.Data.DataSet> de la lista desplegable en la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A>.  
  
    2.  Seleccione la tabla principal \(por ejemplo, "Customers"\) de la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A>.  
  
7.  Configure el control <xref:System.Windows.Forms.DataGrid> que desee designar como cuadrícula de detalles, como se detalla a continuación:  
  
    1.  Seleccione el objeto <xref:System.Data.DataSet> de la lista desplegable en la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A>.  
  
    2.  Seleccione la relación \(por ejemplo, "Customers.CustOrd"\) entre la tabla principal y la tabla de detalles en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A>.  Para ver la relación, expanda el nodo, para ello, haga clic en el signo más \(**\+**\) que aparece junto a la tabla maestra en la lista desplegable.  
  
## Vea también  
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Enlazar controles a los datos en Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)