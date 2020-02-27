---
title: Impedir la adición y eliminación de filas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628896"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador
En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>. Las nuevas filas se escriben en la fila especial para los nuevos registros en la parte inferior del control. Al deshabilitar la adición de filas, no se muestra la fila de los nuevos registros. Después, puede hacer que el control sea completamente de solo lectura deshabilitando la eliminación de filas y la edición de celdas.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-prevent-row-addition-and-deletion"></a>Para evitar la adición y eliminación de filas

- Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, desactive las casillas **Habilitar agregar** y **Habilitar eliminación** .

    > [!NOTE]
    > Para que el control sea completamente de solo lectura, desactive también la casilla **Habilitar edición** .

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
