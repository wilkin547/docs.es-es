---
title: "C&#243;mo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Dise&#241;ador | Microsoft Docs"
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
  - "controles enlazados"
  - "controles enlazados, DataGrid (control)"
  - "enlace de datos, DataGrid (control)"
  - "controles enlazados a datos, DataGrid"
  - "DataGrid (control) [Windows Forms], enlace de datos"
  - "conjuntos de datos [Windows Forms], enlazar a un control DataGrid"
  - "controles de Windows Forms, enlace de datos"
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Dise&#241;ador
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 El control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms está diseñado especialmente para mostrar información sobre un origen de datos.  El control se enlaza en tiempo de diseño estableciendo las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> o en tiempo de ejecución llamando al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  Aunque se pueden mostrar datos de diversos orígenes de datos, los más comunes son los conjuntos de datos y las vistas de datos.  
  
 Si el origen de datos está disponible en tiempo de diseño, por ejemplo, si el formulario contiene una instancia de un conjunto de datos o de una vista de datos, se puede enlazar la cuadrícula a ese origen de datos en tiempo de diseño.  A continuación, se puede realizar una vista previa del aspecto que tendrán los datos en la cuadrícula.  
  
 También se puede enlazar la cuadrícula mediante programa, en tiempo de ejecución.  Esto resulta útil si se desea establecer un origen de datos basado en información que se obtiene en tiempo de ejecución.  Por ejemplo, la aplicación puede permitir al usuario especificar el nombre de la tabla que desea ver.  También resulta necesario en situaciones en las que el origen de datos no existe en tiempo de diseño.  Esto incluye orígenes de datos tales como matrices, colecciones, conjuntos de datos sin tipo y lectores de datos.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGrid>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], el control <xref:System.Windows.Forms.DataGrid> no está en el **Cuadro de herramientas** de manera predeterminada.  Para obtener información sobre cómo agregarlo, vea [How to: Add Items to the Toolbox](http://msdn.microsoft.com/es-es/458e119e-17fe-450b-b889-e31c128bd7e0).  Además en [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], se puede utilizar la ventana **Orígenes de datos** para el enlace de datos en tiempo de diseño.  Para obtener más información, vea [Enlazar controles a los datos en Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para enlazar el control DataGrid a una sola tabla en el diseñador  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A> del control en el objeto que contenga los elementos de datos con los que desea enlazarlo.  
  
2.  Si el origen de datos es un conjunto de datos, establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A> en el nombre de la tabla objeto del enlace.  
  
3.  Si el origen de datos es un conjunto de datos o una vista de datos basado en una tabla de un conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto depende del lugar del que vaya a obtener los datos el conjunto de datos.  Si el conjunto de datos se va a rellenar directamente a partir de la base de datos, normalmente se invoca al método `Fill` de un adaptador de datos, como en el ejemplo de código siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  \(Opcional\) Agregue los estilos de tabla y de columna adecuados a la cuadrícula.  
  
     Si no hay estilos de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
### Para enlazar el control DataGrid a varias tablas de un conjunto de datos en el diseñador  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A> del control en el objeto que contenga los elementos de datos con los que desea enlazarlo.  
  
2.  Si el conjunto de datos contiene tablas relacionadas \(es decir, si contiene un objeto Relation\), establezca la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A> en el nombre de la tabla primaria.  
  
3.  Escriba código para llenar el conjunto de datos.  
  
## Vea también  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Obtener acceso a los datos en Visual Studio](../Topic/Accessing%20data%20in%20Visual%20Studio.md)