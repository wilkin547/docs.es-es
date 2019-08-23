---
title: Procedimiento para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 7a3029192ab0da4a954dfd7d3d258a00b154924e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957112"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
El control <xref:System.Windows.Forms.DataGridView> Windows Forms debe contener columnas para poder mostrar los datos. Si tiene previsto rellenar el control manualmente, debe agregar las columnas. Como alternativa, puede enlazar el control a un origen de datos, que genera y rellena automáticamente las columnas. Si el origen de datos contiene más columnas de las que desea mostrar, puede quitar las columnas no deseadas.

 Los procedimientos siguientes requieren un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-add-a-column-using-the-designer"></a>Para agregar una columna mediante el diseñador

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y seleccione **Agregar columna**.

2. En el cuadro de diálogo **Agregar columna** , elija la opción de **columna DataBound** y seleccione una columna del origen de datos o elija la opción **columna** sin enlazar y defina la columna con los campos proporcionados.

3. Haga clic en el botón **Agregar** para agregar la columna, lo que hará que aparezca en el diseñador si las columnas existentes aún no rellenan el área de presentación del control.

    > [!NOTE]
    > Puede modificar las propiedades de las columnas en el cuadro de diálogo **Editar columnas** , al que puede tener acceso desde la etiqueta inteligente del control.

## <a name="to-remove-a-column-using-the-designer"></a>Para quitar una columna mediante el diseñador

1. Elija **Editar columnas** en la etiqueta inteligente del control.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. Haga clic en el botón **quitar** para eliminar la columna, lo que hará que desaparezca del diseñador.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Cómo: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
