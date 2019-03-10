---
title: Procedimiento Crear listas principal-detalle con el Control DataGrid de Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 0bf967ed364447782c8e8df4c86ac32371ac880f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705160"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Procedimiento Crear listas principal-detalle con el Control DataGrid de Windows Forms mediante el diseñador

> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Si su <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato de pantalla principal-detallada. Una <xref:System.Windows.Forms.DataGrid> se designa como la cuadrícula principal, y el segundo se designa como la cuadrícula de detalles. Cuando se selecciona una entrada en la lista maestra, todas las entradas secundarias relacionadas aparecen en la lista de detalles. Por ejemplo, si su <xref:System.Data.DataSet> contiene una tabla Customers y una tabla de pedidos relacionada, debe especificar la tabla de clientes para la cuadrícula principal y la tabla Orders y cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula principal, todos los pedidos asociados a ese cliente en la tabla Orders se mostraría en la cuadrícula de detalles.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **Windows Forms Aplicación**).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Para crear una lista de detalles principales en el diseñador  
  
1.  Agregue dos <xref:System.Windows.Forms.DataGrid> controles al formulario. Para obtener más información, vea [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener más información, vea [Cómo: Agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).  
  
    > [!NOTE]
    >  Los pasos siguientes no son aplicables a Visual Studio 2005, que usa el **orígenes de datos** ventana para el enlace de datos en tiempo de diseño. Para obtener más información, consulte [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) y [Cómo: Mostrar relacionados con datos en un Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).  
  
2.  Arrastre dos o más tablas de **Explorador de servidores** al formulario.  
  
3.  Desde el **datos** menú, seleccione **Generar conjunto de datos**.  
  
4.  Establecer las relaciones entre las tablas mediante el Diseñador XML. Para obtener más información, vea "Cómo: Crear relaciones de uno a varios en esquemas XML y conjuntos de datos"en MSDN.  
  
5.  Guarde la relación seleccionando **guardar todo** desde el **archivo** menú.  
  
6.  Configurar el <xref:System.Windows.Forms.DataGrid> control que desea designar como cuadrícula principal, como se indica a continuación:  
  
    1.  Seleccione el <xref:System.Data.DataSet> en la lista desplegable en el <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad.  
  
    2.  Seleccione la tabla principal (por ejemplo, "Customers") en la lista desplegable en el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad.  
  
7.  Configurar el <xref:System.Windows.Forms.DataGrid> control que desea designar la cuadrícula de detalles, como se indica a continuación:  
  
    1.  Seleccione el <xref:System.Data.DataSet> en la lista desplegable en el <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad.  
  
    2.  Seleccione la relación (por ejemplo, "Customers.CustOrd") entre las tablas de maestro y detalles de la lista desplegable en el <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad. Para ver la relación, expanda el nodo, haga clic en el signo más (**+**) aparece junto a la tabla maestra en la lista desplegable.  
  
## <a name="see-also"></a>Vea también
- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
