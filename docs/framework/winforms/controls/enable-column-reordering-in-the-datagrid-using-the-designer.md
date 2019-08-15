---
title: Procedimiento para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 3864ce70f058259b597df904311bd4a48218b151
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040343"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
Al ver los datos mostrados en <xref:System.Windows.Forms.DataGridView> un control de Windows Forms, a veces los usuarios desean comparar los valores de columnas específicas. Esto puede ser inconveniente si las columnas están ampliamente separadas en el control, especialmente si los usuarios deben desplazarse horizontalmente para ver todas las columnas en las que están interesados. Puede facilitar la tarea de comparar los valores de columna si permite que los usuarios reordenen las columnas. Al habilitar la reordenación de columnas, los usuarios pueden mover una columna a una nueva posición arrastrando el encabezado de columna con el mouse.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-enable-column-reordering"></a>Para habilitar la reordenación de columnas

- Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y seleccione **Habilitar**reordenación de columnas.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Procedimientos: Inmovilizar columnas en el control DataGridView Windows Forms mediante el diseñador](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
