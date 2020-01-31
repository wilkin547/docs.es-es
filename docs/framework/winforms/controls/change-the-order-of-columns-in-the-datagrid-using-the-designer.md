---
title: Cambiar el orden de las columnas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: be4f67ca6530b74fc90cb50a10463b2378edb933
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743157"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador

Al enlazar un Windows Forms <xref:System.Windows.Forms.DataGridView> control a un origen de datos, el orden de presentación de las columnas generadas automáticamente viene determinado por el origen de datos. Si este orden no es el preferido, puede cambiar el orden de las columnas mediante el diseñador. También puede que desee agregar columnas sin enlazar al control y cambiar el orden de visualización. Para obtener información sobre cómo cambiar el orden de las columnas mediante programación, vea [Cómo: cambiar el orden de las columnas en el control DataGridView Windows Forms](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-change-the-column-order-using-the-designer"></a>Para cambiar el orden de las columnas mediante el diseñador

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. Haga clic en la flecha arriba o abajo situada a la derecha de la lista **columnas seleccionadas** hasta que la columna seleccionada se encuentra en la posición deseada.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
