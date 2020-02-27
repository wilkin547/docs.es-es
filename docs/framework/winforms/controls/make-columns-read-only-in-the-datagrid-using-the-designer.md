---
title: Crear columnas de solo lectura en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 2dd3f8bfcad39ca3d530c79a6e6a8170585f7adf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627960"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms mediante el Diseñador
De forma predeterminada, los usuarios pueden modificar los datos numéricos y de texto que se muestran en el control Windows Forms <xref:System.Windows.Forms.DataGridView>. Si desea mostrar datos que no están diseñados para su modificación, debe hacer que las columnas que contienen los datos sean de solo lectura. Para obtener información sobre cómo hacer que el control sea completamente de solo lectura, vea [Cómo: impedir la adición y eliminación de filas en el control Windows Forms DataGridView mediante el diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>Para hacer que una columna sea de solo lectura mediante el diseñador

1. Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. En la cuadrícula **propiedades de columna** , establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> en `true`.

    > [!NOTE]
    > También puede hacer que una columna sea de solo lectura al agregarla activando la casilla **solo lectura** en el cuadro de diálogo **Agregar columna** .

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
