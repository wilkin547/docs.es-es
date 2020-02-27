---
title: Cambiar el orden de las columnas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628753"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador

Al enlazar un Windows Forms <xref:System.Windows.Forms.DataGridView> control a un origen de datos, el orden de presentación de las columnas generadas automáticamente viene determinado por el origen de datos. Si este orden no es el preferido, puede cambiar el orden de las columnas mediante el diseñador. También puede que desee agregar columnas sin enlazar al control y cambiar el orden de visualización. Para obtener información sobre cómo cambiar el orden de las columnas mediante programación, vea [Cómo: cambiar el orden de las columnas en el control DataGridView Windows Forms](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-change-the-column-order-using-the-designer"></a>Para cambiar el orden de las columnas mediante el diseñador

1. Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. Haga clic en la flecha arriba o abajo situada a la derecha de la lista **columnas seleccionadas** hasta que la columna seleccionada se encuentra en la posición deseada.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- [Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
