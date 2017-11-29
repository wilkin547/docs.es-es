---
title: "Cómo: Crear listas Principal-Detalle con el control DataGrid de Windows Forms mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66de6fb17e3ee5b916c4bb20dfa0799758375406
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Cómo: Crear listas Principal-Detalle con el control DataGrid de Windows Forms mediante el Diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Si su <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato principal-detalle. Una <xref:System.Windows.Forms.DataGrid> está designado como la cuadrícula principal, y el segundo está designado como la cuadrícula de detalles. Cuando se selecciona una entrada en la lista maestra, todas las entradas secundarias relacionadas aparecen en la lista de detalles. Por ejemplo, si su <xref:System.Data.DataSet> contiene una tabla Customers y una tabla relacionada Orders, se especificaría la tabla Customers como cuadrícula principal y la tabla Orders como cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula principal, se mostraría todos los pedidos asociados a ese cliente en la tabla Orders en la cuadrícula de detalles.  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Para crear una lista principal-detalle en el diseñador  
  
1.  Agregar dos <xref:System.Windows.Forms.DataGrid> controles al formulario. Para obtener más información, consulte [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener más información, consulte [Cómo: agregar elementos al cuadro de herramientas](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Los pasos siguientes no son aplicables a [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], que usa el **orígenes de datos** ventana para el enlace de datos en tiempo de diseño. Para obtener más información, consulte [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) y [Cómo: mostrar datos relacionados en una aplicación de Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  Arrastre dos o más tablas de **Explorador de servidores** al formulario.  
  
3.  Desde el **datos** menú, seleccione **Generar conjunto de datos**.  
  
4.  Establecer las relaciones entre las tablas mediante el Diseñador XML. Para obtener más información, vea "Cómo: crear uno a varios las relaciones en esquemas XML y conjuntos de datos" en MSDN.  
  
5.  Guarde la relación seleccionando **guardar todo** desde el **archivo** menú.  
  
6.  Configurar el <xref:System.Windows.Forms.DataGrid> control que desea designar como cuadrícula principal, como se indica a continuación:  
  
    1.  Seleccione el <xref:System.Data.DataSet> en la lista desplegable de la <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad.  
  
    2.  Seleccione la tabla principal (por ejemplo, "Customers") en la lista desplegable de la <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad.  
  
7.  Configurar el <xref:System.Windows.Forms.DataGrid> control que desea designar como cuadrícula de detalles, como se indica a continuación:  
  
    1.  Seleccione el <xref:System.Data.DataSet> en la lista desplegable de la <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad.  
  
    2.  Seleccione la relación (por ejemplo, "Customers.CustOrd") entre las tablas de maestro y detalles de la lista desplegable en el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad. Para ver la relación, expanda el nodo, haga clic en el signo más (**+**) aparece junto a la tabla maestra en la lista desplegable.  
  
## <a name="see-also"></a>Vea también  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
