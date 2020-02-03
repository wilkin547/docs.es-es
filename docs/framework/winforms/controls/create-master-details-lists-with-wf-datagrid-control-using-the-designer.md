---
title: Crear listas principal-detalle con el control DataGrid mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 0dea3dd88a8c6c2aceb894789ace8ef3b5c83632
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743388"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Cómo: Crear listas Principal-Detalle con el control DataGrid de Windows Forms mediante el Diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

 Si el <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede usar dos controles <xref:System.Windows.Forms.DataGrid> para mostrar los datos en un formato maestro-detalle. Una <xref:System.Windows.Forms.DataGrid> se designa como cuadrícula maestra y la segunda se designa como cuadrícula de detalles. Al seleccionar una entrada en la lista maestra, todas las entradas secundarias relacionadas se muestran en la lista de detalles. Por ejemplo, si el <xref:System.Data.DataSet> contiene una tabla Customers y una tabla Orders relacionada, debe especificar la tabla Customers como cuadrícula maestra y la tabla Orders como cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula maestra, todos los pedidos asociados a ese cliente en la tabla Orders se mostrarán en la cuadrícula detalles.

 El procedimiento siguiente requiere un proyecto de **aplicación de Windows** (**archivo** > **nuevo** **proyecto** de >  > **Visual C#**  o **Visual Basic** > **aplicación**de > de **escritorio clásico** .

## <a name="to-create-a-master-details-list-in-the-designer"></a>Para crear una lista de maestro y detalles en el diseñador

1. Agregue dos controles <xref:System.Windows.Forms.DataGrid> al formulario. Para obtener más información, vea [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el control <xref:System.Windows.Forms.DataGrid> no está en el **cuadro de herramientas** de forma predeterminada. Para obtener más información, vea [Cómo: agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

    > [!NOTE]
    > Los pasos siguientes no son aplicables a Visual Studio 2005, que usa la ventana **orígenes de datos** para el enlace de datos en tiempo de diseño. Para obtener más información, vea [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) y [Cómo: Mostrar datos relacionados en una aplicación Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).

2. Arrastre dos o más tablas desde **Explorador de servidores** al formulario.

3. En el menú datos, seleccione **generar conjunto**de **datos** .

4. Establezca las relaciones entre las tablas mediante el diseñador XML. Para obtener más información, vea "Cómo: crear relaciones uno a varios en esquemas y conjuntos de datos XML" en MSDN.

5. Guarde las relaciones seleccionando **guardar todo** en el menú **archivo** .

6. Configure el control <xref:System.Windows.Forms.DataGrid> que desea designar como la cuadrícula maestra, como se indica a continuación:

    1. Seleccione la <xref:System.Data.DataSet> en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A>.

    2. Seleccione la tabla maestra (por ejemplo, "Customers") en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A>.

7. Configure el control <xref:System.Windows.Forms.DataGrid> que desea designar en la cuadrícula de detalles de la siguiente manera:

    1. Seleccione la <xref:System.Data.DataSet> en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGrid.DataSource%2A>.

    2. Seleccione la relación (por ejemplo, "customers. CustOrd") entre las tablas maestra y de detalles de la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A>. Para ver la relación, expanda el nodo haciendo clic en el signo más ( **+** ) situado junto a la tabla maestra en la lista desplegable.

## <a name="see-also"></a>Consulte también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
