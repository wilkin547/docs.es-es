---
title: Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 6bdd561c863a461f43a5a7aac025fead1f971bb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039816"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador
De forma predeterminada, los usuarios pueden modificar los datos numéricos y de <xref:System.Windows.Forms.DataGridView> texto que se muestran en el control Windows Forms. Si desea mostrar datos que no están diseñados para su modificación, debe hacer que las columnas que contienen los datos sean de solo lectura. Para obtener información sobre cómo hacer que el control sea completamente de solo lectura [, consulte Cómo: Evite la adición y eliminación de filas en el control Windows Forms DataGridView mediante](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)el diseñador.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>Para hacer que una columna sea de solo lectura mediante el diseñador

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. En la cuadrícula **propiedades de columna** , establezca <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> la propiedad `true`en.

    > [!NOTE]
    >  También puede hacer que una columna sea de solo lectura al agregarla activando la casilla **solo lectura** en el cuadro de diálogo **Agregar columna** .

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Impedir la adición y eliminación de filas en el control Windows Forms DataGridView mediante el diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Cómo: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedimientos: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
