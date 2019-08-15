---
title: Procedimiento para enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el diseñador
ms.date: 03/30/2017
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
ms.openlocfilehash: de8b8d16f45221fbafe9f61ca634f144d8f6f6ae
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040011"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Procedimiento para enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el diseñador

> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

 El control <xref:System.Windows.Forms.DataGrid> Windows Forms está diseñado específicamente para mostrar información de un origen de datos. Para enlazar el control en tiempo de diseño, <xref:System.Windows.Forms.DataGrid.DataSource%2A> establezca <xref:System.Windows.Forms.DataGrid.DataMember%2A> las propiedades y, o en tiempo de ejecución <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> mediante una llamada al método. Aunque puede mostrar los datos de diversos orígenes de datos, los orígenes más habituales son los conjuntos de datos y las vistas de datos.

 Si el origen de datos está disponible en tiempo de diseño (por ejemplo, si el formulario contiene una instancia de un conjunto de datos o una vista de datos), puede enlazar la cuadrícula al origen de datos en tiempo de diseño. Después, puede obtener una vista previa de la apariencia de los datos en la cuadrícula.

 También puede enlazar la cuadrícula mediante programación, en tiempo de ejecución. Esto resulta útil cuando se desea establecer un origen de datos basado en la información que se obtiene en tiempo de ejecución. Por ejemplo, la aplicación puede permitir que el usuario especifique el nombre de una tabla para ver. También es necesario en situaciones en las que el origen de datos no existe en tiempo de diseño. Esto incluye orígenes de datos como matrices, colecciones, conjuntos de datos sin tipo y lectores de datos.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGrid> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener información acerca de cómo agregarlo, consulte [cómo: Agregar elementos al cuadro de](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))herramientas. Además, en Visual Studio 2005, puede usar la ventana **orígenes de datos** para el enlace de datos en tiempo de diseño. Para obtener más información, vea [enlazar controles a datos en Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Para enlazar datos al control DataGrid a una sola tabla en el diseñador

1. Establezca la propiedad del <xref:System.Windows.Forms.DataGrid.DataSource%2A> control en el objeto que contiene los elementos de datos a los que desea enlazar.

2. Si el origen de datos es un conjunto de datos <xref:System.Windows.Forms.DataGrid.DataMember%2A> , establezca la propiedad en el nombre de la tabla a la que se va a enlazar.

3. Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.

     El código exacto que se utiliza depende de la ubicación del conjunto de datos. Si el conjunto de datos se rellena directamente desde una base de datos, normalmente `Fill` se llama al método de un adaptador de datos, como en el ejemplo de código siguiente, que `DsCategories1`rellena un conjunto de datos denominado:

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. Opta Agregue los estilos de tabla y de columna correspondientes a la cuadrícula.

     Si no hay ningún estilo de tabla, verá la tabla, pero con el formato mínimo y con todas las columnas visibles.

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Para enlazar datos al control DataGrid en varias tablas de un conjunto de datos en el diseñador

1. Establezca la propiedad del <xref:System.Windows.Forms.DataGrid.DataSource%2A> control en el objeto que contiene los elementos de datos a los que desea enlazar.

2. Si el conjunto de elementos contiene tablas relacionadas (es decir, si contiene un objeto de relación), <xref:System.Windows.Forms.DataGrid.DataMember%2A> establezca la propiedad en el nombre de la tabla primaria.

3. Escriba código para rellenar el conjunto de DataSet.

## <a name="see-also"></a>Vea también

- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Obtener acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
