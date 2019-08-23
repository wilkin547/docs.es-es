---
title: Procedimiento para impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: f47eb29bf9ae077555f352d10c667bac4ade9373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968321"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el diseñador
En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>. Las nuevas filas se escriben en la fila especial para los nuevos registros en la parte inferior del control. Al deshabilitar la adición de filas, no se muestra la fila de los nuevos registros. Después, puede hacer que el control sea completamente de solo lectura deshabilitando la eliminación de filas y la edición de celdas.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-prevent-row-addition-and-deletion"></a>Para evitar la adición y eliminación de filas

- Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, desactive las casillas **Habilitar agregar** y **Habilitar eliminación** .

    > [!NOTE]
    > Para que el control sea completamente de solo lectura, desactive también la casilla **Habilitar edición** .

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Procedimientos: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
