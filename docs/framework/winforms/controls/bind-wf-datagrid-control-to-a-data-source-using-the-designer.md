---
title: "Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador"
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
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 378f1d80392ae7b2058d5c3b2d987e4810cbd07b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control está diseñado específicamente para mostrar información de un origen de datos. Enlazar el control en tiempo de diseño estableciendo la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades, o en tiempo de ejecución mediante una llamada a la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método. Aunque se pueden mostrar datos desde una variedad de orígenes de datos, los orígenes más habituales son vistas de datos y conjuntos de datos.  
  
 Si el origen de datos está disponible en tiempo de diseño, por ejemplo, si el formulario contiene una instancia de un conjunto de datos o una vista de datos, puede enlazar la cuadrícula al origen de datos en tiempo de diseño. A continuación, puede ver el aspecto de los datos en la cuadrícula.  
  
 También puede enlazar mediante programación, la cuadrícula en tiempo de ejecución. Esto es útil cuando desea establecer un origen de datos basado en la información que se obtienen en tiempo de ejecución. Por ejemplo, la aplicación podría permiten al usuario especificar el nombre de tabla que desea ver. También es necesario en situaciones donde el origen de datos no existe en tiempo de diseño. Esto incluye orígenes de datos como matrices, colecciones, conjuntos de datos sin tipo y lectores de datos.  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGrid> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener información sobre cómo agregarlo, vea [Cómo: agregar elementos al cuadro de herramientas](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0). Además de [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], puede usar el **orígenes de datos** ventana para el enlace de datos en tiempo de diseño. Para obtener más información, consulte [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Para enlazar el control DataGrid a una sola tabla en el diseñador  
  
1.  Establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad para el objeto que contiene los elementos de datos que desea enlazar.  
  
2.  Si el origen de datos es un conjunto de datos, establezca la <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad en el nombre de la tabla que se va a enlazar a.  
  
3.  Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto que utilice depende de que el conjunto de datos está obteniendo datos. Si se está llenando el conjunto de datos directamente desde una base de datos, normalmente se invoca el `Fill` método de un adaptador de datos, como en el ejemplo de código siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  (Opcional) Agregar los estilos de tabla adecuado y estilos de columna a la cuadrícula.  
  
     Si no hay ningún estilo de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Para enlazar el control DataGrid a varias tablas en un conjunto de datos en el diseñador  
  
1.  Establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad para el objeto que contiene los elementos de datos que desea enlazar.  
  
2.  Si el conjunto de datos contiene tablas relacionadas (es decir, si contiene un objeto relation), establezca el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad en el nombre de la tabla primaria.  
  
3.  Escribir código para llenar el conjunto de datos.  
  
## <a name="see-also"></a>Vea también  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Obtener acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
