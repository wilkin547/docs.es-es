---
title: Establecer estilos de celda y formatos de datos predeterminados para el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731359"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el diseñador

El control <xref:System.Windows.Forms.DataGridView> permite especificar los estilos de celda y los formatos de datos de celda predeterminados para todo el control, para las columnas específicas, para los encabezados de fila y de columna, y para las filas alternas para crear un efecto de libro. Los estilos predeterminados establecidos para todo el control se reemplazan por los estilos predeterminados establecidos para las columnas y las filas alternas. Además, los estilos que se establecen en el código para filas y celdas individuales reemplazan los estilos predeterminados.

Para obtener más información sobre los estilos de celda, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md). Para establecer estilos para filas alternas, vea [Cómo: establecer estilos de fila alternos para el control DataGridView Windows Forms mediante el diseñador](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).

También puede establecer estilos mediante la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> para que afecten a todas las filas que se van a agregar al control. Para obtener más información sobre la plantilla de fila, consulte [Cómo: utilizar la plantilla de fila para personalizar las filas en el control DataGridView Windows Forms](use-the-row-template-to-customize-rows-in-the-datagrid.md).

Los procedimientos siguientes requieren un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Para establecer estilos predeterminados para todas las celdas del control

1. Seleccione el control <xref:System.Windows.Forms.DataGridView> en el diseñador.

2. En la ventana **propiedades** , haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>. Aparecerá el cuadro de diálogo **generador de CellStyle** .

3. Defina el estilo estableciendo las propiedades mediante el panel de **vista previa** para confirmar las opciones.

> [!NOTE]
> Si los estilos visuales están habilitados, los encabezados de fila y de columna (excepto el <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) se aplican de forma automática al tema actual, invalidando los valores de las propiedades <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.
>
> Puede establecer estilos de celda para varios controles de <xref:System.Windows.Forms.DataGridView> seleccionados mediante el diseñador, pero solo si tienen valores idénticos para la propiedad de estilo de celda que desea modificar. Si hay algún estilo de celda distinto para esa propiedad, las ventanas **propiedades** del cuadro de diálogo **generador de CellStyle** estarán en blanco.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Para establecer estilos predeterminados para las celdas de columnas individuales

1. Haga clic con el botón secundario en el control <xref:System.Windows.Forms.DataGridView> en el diseñador y elija **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. En la cuadrícula **propiedades de columna** , haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>. Aparecerá el cuadro de diálogo **generador de CellStyle** .

4. Defina el estilo estableciendo las propiedades mediante el panel de **vista previa** para confirmar las opciones.

### <a name="to-format-data-in-cells"></a>Para dar formato a los datos de las celdas

1. Use uno de los procedimientos anteriores para mostrar un cuadro de diálogo **generador de CellStyle** relacionado con una propiedad de estilo de celda predeterminada.

2. En el cuadro de diálogo **generador de CellStyle** , haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>. Aparecerá el cuadro de diálogo **cadena de formato** .

3. Seleccione un tipo de formato y, a continuación, modifique los detalles del tipo (por ejemplo, el número de posiciones decimales que se van a mostrar), mediante el cuadro **ejemplo** para confirmar las opciones.

4. Si enlaza el control de <xref:System.Windows.Forms.DataGridView> a un origen de datos que probablemente contenga valores NULL, rellene el cuadro de texto **valor nulo** . Este valor se muestra cuando el valor de la celda es igual a una referencia nula (`Nothing` en Visual Basic) o <xref:System.DBNull.Value?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el Diseñador](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
