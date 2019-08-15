---
title: Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: bf77cf3705a470bbe00be383f6a5cb2d28bda34d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039630"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el diseñador

Al enlazar un control <xref:System.Windows.Forms.DataGridView> de Windows Forms a un origen de datos, el orden de presentación de las columnas generadas automáticamente viene determinado por el origen de datos. Si este orden no es el preferido, puede cambiar el orden de las columnas mediante el diseñador. También puede que desee agregar columnas sin enlazar al control y cambiar el orden de visualización. Para obtener información sobre cómo cambiar el orden de las columnas mediante programación [, consulte Cómo: Cambiar el orden de las columnas en el control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-change-the-column-order-using-the-designer"></a>Para cambiar el orden de las columnas mediante el diseñador

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. Haga clic en la flecha arriba o abajo situada a la derecha de la lista **columnas seleccionadas** hasta que la columna seleccionada se encuentra en la posición deseada.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
