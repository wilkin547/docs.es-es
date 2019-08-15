---
title: Procedimiento para ocultar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: d502a89913e108254848151e9058ac6ae83a9638
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039768"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para ocultar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
Algunas veces querrá mostrar solo algunas de las columnas que están disponibles en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms. Por ejemplo, puede que desee mostrar una columna de sueldo de empleado a los usuarios con credenciales de administración mientras la ocultan de otros usuarios. Como alternativa, puede enlazar el control a un origen de datos que contenga muchas columnas, solo algunas de las cuales desea mostrar. En este caso, normalmente se quitarán las columnas que no le interesa Mostrar en lugar de ocultarlas. Para obtener más información, vea [Cómo: Agregue y quite columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md).

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-hide-a-column-using-the-designer"></a>Para ocultar una columna mediante el diseñador

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. En la cuadrícula **propiedades de columna** , establezca <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> la propiedad `false`en.

    > [!NOTE]
    >  También puede ocultar una columna al agregarla desactivando la casilla **visible** en el cuadro de diálogo **Agregar columna** .

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
