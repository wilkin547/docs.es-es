---
title: Procedimiento para crear listas maestro y detalle con el control DataGrid de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 3962b671176ad158b338889140181834e05bbeee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929724"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Procedimiento para crear listas maestro y detalle con el control DataGrid de formularios Windows Forms mediante el diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

 Si contiene una serie de tablas relacionadas, puede usar dos <xref:System.Windows.Forms.DataGrid> controles para mostrar los datos en un formato maestro-detalle. <xref:System.Data.DataSet> Uno <xref:System.Windows.Forms.DataGrid> se designa como la cuadrícula maestra y el segundo se designa como la cuadrícula de detalles. Al seleccionar una entrada en la lista maestra, todas las entradas secundarias relacionadas se muestran en la lista de detalles. Por ejemplo, si <xref:System.Data.DataSet> contiene una tabla Customers y una tabla Orders relacionada, debe especificar la tabla Customers como cuadrícula maestra y la tabla Orders como cuadrícula de detalles. Cuando se selecciona un cliente en la cuadrícula maestra, todos los pedidos asociados a ese cliente en la tabla Orders se mostrarán en la cuadrícula detalles.

 El procedimiento siguiente requiere un proyecto de **aplicación para Windows** (**archivo** > **nuevo** > **proyecto** > **Visual C#**  o **Visual Basic**  >  > Aplicación de escritorio clásico**Windows Forms**).

## <a name="to-create-a-master-details-list-in-the-designer"></a>Para crear una lista de maestro y detalles en el diseñador

1. Agregue dos <xref:System.Windows.Forms.DataGrid> controles al formulario. Para obtener más información, consulte [Cómo Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener más información, vea [Cómo: Agregar elementos al cuadro de](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))herramientas.

    > [!NOTE]
    > Los pasos siguientes no son aplicables a Visual Studio 2005, que usa la ventana **orígenes de datos** para el enlace de datos en tiempo de diseño. Para obtener más información, vea [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) y [cómo: Mostrar datos relacionados en una aplicación](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))Windows Forms.

2. Arrastre dos o más tablas desde **Explorador de servidores** al formulario.

3. En el menú datos, seleccione **generar conjunto**de **datos** .

4. Establezca las relaciones entre las tablas mediante el diseñador XML. Para obtener más información, consulte "Cómo: Crear relaciones uno a varios en esquemas XML y conjuntos de valores "en MSDN.

5. Guarde las relaciones seleccionando **guardar todo** en el menú **archivo** .

6. Configure <xref:System.Windows.Forms.DataGrid> el control que desea designar como la cuadrícula maestra, como se indica a continuación:

    1. Seleccione en la lista desplegable de la <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad. <xref:System.Data.DataSet>

    2. Seleccione la tabla maestra (por ejemplo, "Customers") en la lista desplegable de la <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedad.

7. Configure <xref:System.Windows.Forms.DataGrid> el control que desea designar en la cuadrícula de detalles de la siguiente manera:

    1. Seleccione en la lista desplegable de la <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedad. <xref:System.Data.DataSet>

    2. Seleccione la relación (por ejemplo, "customers. CustOrd") entre las tablas maestra y de detalles de la lista desplegable de <xref:System.Windows.Forms.DataGrid.DataMember%2A> la propiedad. Para ver la relación, expanda el nodo haciendo clic en el signo más ( **+** ) situado junto a la tabla maestra en la lista desplegable.

## <a name="see-also"></a>Vea también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Enlazar controles a los datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
